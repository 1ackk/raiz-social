<div align="center">

# 🌱 RaízSocial

**La red social para plantófilos: no compres, intercambia.**

Comparte el cuidado de tu colección y haz trueque de esquejes, semillas y plantas con gente de tu zona.

![Estado](https://img.shields.io/badge/estado-en%20desarrollo-green)
![Laravel](https://img.shields.io/badge/backend-Laravel-FF2D20?logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/frontend-React-61DAFB?logo=react&logoColor=black)
![MySQL](https://img.shields.io/badge/BD-MySQL-4479A1?logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/despliegue-Docker-2496ED?logo=docker&logoColor=white)

</div>

---

## 📖 ¿Qué es RaízSocial?

RaízSocial es una red social de nicho pensada para amantes de las plantas. Combina dos ideas:

- **Comunidad:** enseña tu colección, publica, comenta y sigue a otros plantófilos.
- **Economía circular:** en vez de comprar una planta nueva, la intercambias con alguien cercano.

Es el Trabajo de Fin de Grado (TFG) de Desarrollo Web de un equipo de tres personas.

## 💡 Propuesta de valor

| Qué ofrece | Por qué importa |
|---|---|
| Intercambio en lugar de compra | Ahorro, sostenibilidad y plantas que no se encuentran en tiendas |
| Comunidad local | El trueque funciona porque el otro vive cerca |
| Reputación por intercambios | Valoraciones mutuas que generan confianza |
| Datos propios por zona | Qué especies se piden y se ofrecen en cada área |

## ✨ Funcionalidades

### Social
- Perfiles de usuario
- **Mi jardín:** las plantas de cada usuario
- Posts, likes y comentarios
- Seguir a otros usuarios
- Grupos temáticos

### Intercambio
- Anuncios **"ofrezco / busco"**
- Filtros por ubicación y tipo de planta
- Propuestas de intercambio con estados: `pendiente` → `aceptada` / `rechazada` → `completada`
- Valoraciones mutuas al completar

### Administración
- Gestión de reportes y de usuarios

### 🧪 Opcionales (si el tiempo lo permite)
- Chat y notificaciones en directo
- Mapa de intercambios
- Identificación de plantas por foto
- Recomendaciones

> **Filosofía del proyecto:** pocas funcionalidades bien terminadas antes que muchas a medias. El núcleo es Social + Intercambio; lo opcional solo entra si el núcleo está sólido.

## 🛠️ Stack tecnológico

| Capa | Tecnología |
|---|---|
| Backend | Laravel (API REST) |
| Frontend | React + Vite, Tailwind CSS, React Router |
| Base de datos | MySQL |
| Despliegue | Docker Compose |
| Testing | Pest (backend) · Jest + React Testing Library (frontend) |

## 🏗️ Arquitectura

```
┌────────────────┐   HTTP / JSON   ┌────────────────┐        ┌─────────┐
│  React + Vite  │ ──────────────► │  Laravel API   │ ─────► │  MySQL  │
│  (SPA)         │ ◄────────────── │  (REST)        │ ◄───── │         │
└────────────────┘                 └────────────────┘        └─────────┘
        └──────────── Docker Compose ────────────────┘
```

## 🚀 Puesta en marcha

### Requisitos
- [Docker](https://docs.docker.com/get-docker/) y Docker Compose
- Git

### Instalación

```bash
# 1. Clonar el repositorio
git clone https://github.com/<organizacion>/raizsocial.git
cd raizsocial

# 2. Variables de entorno
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env

# 3. Levantar los servicios
docker compose up -d --build

# 4. Migraciones y datos de ejemplo
docker compose exec backend php artisan key:generate
docker compose exec backend php artisan migrate --seed
```

| Servicio | URL |
|---|---|
| Frontend | http://localhost:5173 |
| API | http://localhost:8000/api |

> ⚠️ Ajusta rutas, puertos y nombres de servicio a tu `docker-compose.yml` real.

## 🧪 Tests

```bash
# Backend
docker compose exec backend ./vendor/bin/pest

# Frontend
docker compose exec frontend npm test
```

## 📁 Estructura del repositorio

```
raizsocial/
├── backend/            # API Laravel
├── frontend/           # SPA React + Vite
├── docker-compose.yml
└── README.md
```

## 👥 Equipo

| Persona | Responsabilidad |
|---|---|
| **Zaida** | Frontend |
| **Ian** | Backend |
| **Javi** | Base de datos |

## 🗺️ Hoja de ruta

- [ ] Autenticación y perfiles
- [ ] Mi jardín
- [ ] Posts, likes y comentarios
- [ ] Anuncios de intercambio con filtros
- [ ] Propuestas de intercambio y estados
- [ ] Valoraciones mutuas
- [ ] Panel de moderación
- [ ] Opcionales (chat, mapa, recomendaciones)

## 📄 Licencia

Proyecto académico desarrollado como TFG. Licencia por definir.

---

<div align="center">
Hecho con 🌿 por el equipo de RaízSocial
</div>
