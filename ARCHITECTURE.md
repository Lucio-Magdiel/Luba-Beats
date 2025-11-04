# 🏗️ Architecture - Luba Beats

## Visión General del Sistema

Luba Beats es una plataforma de streaming musical con un marketplace integrado de beats.


## 🎯 Componentes Principales

### Frontend (Next.js 14)
- Next.js App Router
- React 18+
- Tailwind CSS + Shadcn/ui
- TypeScript

### Backend (Express.js)
- Express.js
- TypeScript
- Supabase Client
- Cloudinary SDK

### Base de Datos (Supabase PostgreSQL)
- RLS por rol
- Realtime subscriptions
- Auth integrado

### Storage (Cloudinary)
- Audio: WAV, MP3 (máx 40MB)
- Imágenes: JPG, PNG, WebP (máx 20MB)

## 🔐 Roles y Permisos

OYENTE: Ver tracks, dar likes, comentar ARTISTA: Oyente + subir canciones PRODUCTOR: Artista + vender beats SUPERADMIN: Gestión total


## 🚀 Deployment
- Frontend: Next.js → Vercel
- Backend: Express → Railway/Render
- Database: Supabase PostgreSQL
- Storage: Cloudinary CDN


│ FRONTEND (Next.js) - Vercel 
│ └──────────────┬──────────────────────────┘ 
│ ↓ ┌─────────────────────────────────────────┐ 
│ BACKEND (Express) - Railway/Render 
│ └──────────────┬──────────────────────────┘ 
│ ┌──────────┼──────────┐ ↓ ↓ ↓ ┌────────┐ ┌─────────┐ ┌────────┐ 
│Supabase│ │Cloudinary│ │ Kahio │ │ (DB) │ │(Storage) │ │(Pagos)│ 
└────────┘ └─────────┘ └────────┘
