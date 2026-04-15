<p align="end">
   <strong>🌐 Change language:</strong><br>
   <a href="README.es.md">
    <img src="https://github.com/Nachopuerto95/multilang/blob/main/ES.png" alt="Español" width="50">
  </a>&nbsp;&nbsp;&nbsp;
  <a href="/README.md">
    <img src="https://github.com/Nachopuerto95/multilang/blob/main/EN.png" alt="English" width="50">
  </a>
</p>

# 🍔 Restaurants

<p align="center">
  <img src="https://github.com/Nachopuerto95/Nachopuerto95/blob/main/assets/restaurants.gif?raw=true" alt="Restaurants demo" width="600"/>
</p>

## 📜 About

Restaurants is a Just-Eat-style web where you look for places to eat near your location, read reviews from other users and leave your own. The map and geocoding come from the Google Maps APIs; the rest (users, restaurants, reviews) lives in our own Express + MongoDB backend.

> [!NOTE]
> Proyecto en pausa / work in progress — el core funciona pero el flujo completo todavía tiene puntas sueltas.

## ✨ What it does

- **Geolocation + autocomplete**: pick your location or type an address with Google's autocomplete.
- **Restaurant search** via `@googlemaps/google-maps-services-js`.
- **Restaurant detail** pages with comments from the community.
- **Auth**: register / login with JWT + bcrypt.
- **Community view**: reviews aggregated across restaurants.
- **Forms** built with `react-hook-form`.

## 🧱 Stack

**Backend (`api/`)**
- Node.js + Express
- MongoDB
- `@googlemaps/google-maps-services-js`
- JWT + bcrypt
- `uuid`, `morgan`
- CORS middleware

**Frontend (`web/`)**
- React 18 + Vite
- `react-router-dom`
- `axios`
- `react-hook-form`
- Tailwind CSS
- Context providers for location and alerts

## 🔧 Run locally

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

`.env` files:

- `api/.env` → `MONGO_URI`, `JWT_SECRET`, `GOOGLE_MAPS_API_KEY`
- `web/.env` → `VITE_GOOGLE_MAPS_API_KEY`, `VITE_API_URL`

## 📂 Layout

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

## 🚀 Deploy

Not deployed yet — the frontend is ready for any static host and the API can drop into Fly.io / Railway with a `fly.toml` when I get back to it.
