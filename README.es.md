<p align="end">
   <strong>🌐 Cambiar idioma:</strong><br>
   <a href="/README.es.md">
    <img src="https://github.com/Nachopuerto95/multilang/blob/main/ES.png" alt="Español" width="50">
  </a>&nbsp;&nbsp;&nbsp;
  <a href="/README.md">
    <img src="https://github.com/Nachopuerto95/multilang/blob/main/EN.png" alt="English" width="50">
  </a>
</p>

# 🍔 Restaurants

<p align="center">
  <img src="https://github.com/Nachopuerto95/Nachopuerto95/blob/main/assets/restaurants.gif?raw=true" alt="Demo de Restaurants" width="600"/>
</p>

## 📜 Sobre el proyecto

Restaurants es una web estilo Just Eat donde buscas sitios para comer cerca de ti, lees reseñas de otros usuarios y dejas las tuyas. El mapa y el geocoding los pone Google Maps; el resto (usuarios, restaurantes, reseñas) vive en un backend propio de Express + MongoDB.

> [!NOTE]
> Proyecto en pausa / work in progress — el core funciona pero el flujo completo todavía tiene puntas sueltas.

## ✨ Qué hace

- **Geolocalización + autocompletado**: eliges ubicación o escribes una dirección con el autocomplete de Google.
- **Búsqueda de restaurantes** usando `@googlemaps/google-maps-services-js`.
- **Páginas de detalle** por restaurante con los comentarios de la comunidad.
- **Auth**: registro / login con JWT + bcrypt.
- **Vista de comunidad**: reseñas agregadas de todos los restaurantes.
- **Formularios** con `react-hook-form`.

## 🧱 Stack

**Backend (`api/`)**
- Node.js + Express
- MongoDB
- `@googlemaps/google-maps-services-js`
- JWT + bcrypt
- `uuid`, `morgan`
- middleware de CORS

**Frontend (`web/`)**
- React 18 + Vite
- `react-router-dom`
- `axios`
- `react-hook-form`
- Tailwind CSS
- Providers de contexto para ubicación y alertas

## 🔧 Ejecución local

```bash
# Backend
cd api
npm install
npm run dev        # http://localhost:3000

# Frontend
cd web
npm install
npm run dev        # http://localhost:5173
```

Ficheros `.env`:

- `api/.env` → `MONGO_URI`, `JWT_SECRET`, `GOOGLE_MAPS_API_KEY`
- `web/.env` → `VITE_GOOGLE_MAPS_API_KEY`, `VITE_API_URL`

## 📂 Estructura

```
Restaurants_WEB/
├── api/
│   ├── controllers/   # restaurants, users, comments
│   ├── models/        # User, Restaurant, Comments
│   ├── routes/
│   └── configs/
└── web/
    ├── src/
    │   ├── pages/     # Home, Register, Login, Community, Restaurants
    │   ├── components/
    │   ├── context/   # AlertProvider, LocationProvider
    │   └── services/
    └── vite.config.js
```

## 🚀 Despliegue

Aún sin desplegar — el frontend está listo para cualquier host estático y la API puede caer en Fly.io / Railway con un `fly.toml` cuando retome el proyecto.
