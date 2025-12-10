# 🛒 ShopLink – Proyecto Final Integrador

> Plataforma completa **ShopLink**, compuesta por un **Frontend en React** y un **Backend en Node + Express + TypeScript**, desarrollada como resolución del Trabajo Práctico **“Desarrollo y Deploy de una API REST en TypeScript”** de la UTN. fileciteturn28file0

---

## 👤 Datos del Autor

- **Nombre:** Alexis Esteban Roldan  
- **Rol:** Estudiante de Desarrollo Full Stack 
- **Mail de contacto:** `a.eroldan@hotmail.com`  
- **GitHub:** [@alexlpda1420](https://github.com/alexlpda1420)  
- **LinkedIn:** [Alexis Esteban Roldan](https://www.linkedin.com/in/alexis-esteban-roldan/)

---

## 🎯 Objetivo del Proyecto

El objetivo fue construir una **aplicación web completa** que combine:

- 🧩 **Frontend** moderno, responsive y usable.  
- 🧠 **Backend** robusto, tipado en TypeScript, con buenas prácticas.  
- ☁️ **Deploy** en producción para que cualquier usuario pueda probar la app.  

Todo esto cumpliendo con la consigna del TP:

- API REST en TypeScript con arquitectura MVC, autenticación, validaciones, logs, rate limit, subida de archivos y deploy en Render. fileciteturn28file0
- Frontend que consuma esa API en producción (Vercel).

---

## 🌐 Links en Producción

### 🔵 Frontend – ShopLink

- **URL:** https://frontend-utn-jade.vercel.app/  

Aplicación web donde se puede:

- Ver, filtrar y buscar productos.  
- Registrarse e iniciar sesión.  
- Agregar, editar y eliminar productos (según permisos).  
- Enviar consultas a través del formulario de contacto.  

### 🟣 Backend – API REST

- **URL:** https://backend-utn-1gp5.onrender.com/  

Expone endpoints para:

- Autenticación (`/auth/register`, `/auth/login`).  
- Gestión de productos (`/products`, filtros, creación, actualización, eliminación).  
- Envío de correos (`/email/send`).  

---

## 📦 Repositorios

### 💻 Frontend

- **Repo:** https://github.com/alexlpda1420/frontend-utn  

Incluye:

- Código de la SPA en React + Vite.  
- Contexto de autenticación, rutas protegidas, filtros, subida de imágenes, etc.  
- Estilos custom en CSS con temática tecnológica y dark mode.  
- README específico del frontend con instrucciones de instalación y uso.

### 🧠 Backend

- **Repo:** https://github.com/alexlpda1420/backend_utn  

Incluye:

- API REST en Node.js + Express + TypeScript + MongoDB.  
- Autenticación con JWT, validaciones con Zod, subida de archivos con Multer.  
- Envío de correos mediante Resend (reemplazo de Nodemailer para Render).  
- Logger con morgan, rate limiting, manejo de errores.  
- README específico del backend con endpoints y configuración.

---

## 🏗️ Arquitectura General

```text
ShopLink
├─ Frontend  → React + Vite (Vercel)
│   ├─ Rutas públicas: Home, Sobre Nosotros, Login, Registro, Contacto
│   ├─ Rutas protegidas: Gestión de productos, Mi Perfil, Mi Carrito
│   └─ Consumo de la API vía fetch/axios contra el backend en Render
└─ Backend   → Node + Express + TypeScript (Render)
    ├─ MVC: controllers, models, routes, middleware, services
    ├─ MongoDB Atlas para almacenamiento de usuarios y productos
    └─ Integraciones: Resend (emails), Multer (uploads)
```

---

## 🧰 Tecnologías Principales

### Frontend

- ⚛️ **React** + **Vite**  
- 🌐 **React Router DOM**  
- 🎨 **CSS** personalizado (layout tecnológico, dark theme, responsive)  
- 🔔 **SweetAlert2** para feedback visual  
- 🧠 Context API para autenticación  
- 📦 Fetch API para comunicación con el backend

### Backend

- 🟩 **Node.js** + **Express**  
- 💙 **TypeScript**  
- 🍃 **MongoDB** + **Mongoose**  
- 🔐 **JWT** + **bcryptjs**  
- 📏 **Zod** (validaciones de inputs)  
- 📸 **Multer** (subida de imágenes)  
- ✉️ **Resend** (emails de contacto y bienvenida)  
- 🧾 **morgan** (logger HTTP)  
- 🚦 **express-rate-limit** (rate limiting)

---

## 🧪 Funcionalidades Clave

### 🔐 Autenticación

- Registro y login de usuarios con validación en backend.  
- Contraseñas hasheadas con bcrypt.  
- Tokens JWT almacenados y utilizados en el frontend para rutas protegidas.  

### 📦 Gestión de Productos

- CRUD completo de productos desde el frontend.  
- Subida de imágenes con Multer y visualización desde uploads servidos por el backend.  
- Filtros por:
  - Categoría  
  - Nombre (búsqueda parcial)  
  - Precio mínimo y máximo  
  - Stock  

> El filtrado se ejecuta directamente en la consulta a MongoDB, como requiere la consigna del TP. fileciteturn28file0

### ✉️ Envío de Correos

- Formulario de contacto en el frontend.  
- Backend envía un correo usando Resend al recibir `POST /email/send`.  
- Email de bienvenida al registrarse un usuario nuevo.

---

## 🏃 Cómo Probar el Proyecto

### 1. Usar la versión en producción (recomendado)

1. Ingresar a **ShopLink (Frontend):**  
   👉 https://frontend-utn-jade.vercel.app/  

2. Crear un usuario desde la vista de **Registro**.  
3. Iniciar sesión y explorar:
   - Home + filtros de productos.  
   - Alta / edición / eliminación de productos.  
   - Página “Mi Perfil” y “Mi Carrito”.  
   - Formulario de contacto.  

> Toda la app se comunica contra el backend desplegado en Render:  
> `https://backend-utn-1gp5.onrender.com/`

### 2. Ejecutar de forma local

Cada repo tiene su propio README detallado. Resumen:

#### 🔵 Frontend local

```bash
git clone https://github.com/alexlpda1420/frontend-utn.git
cd frontend-utn
npm install
npm run dev
```

Abrir: `http://localhost:5173/` (o el puerto que indique Vite).

#### 🟣 Backend local

```bash
git clone https://github.com/alexlpda1420/backend_utn.git
cd backend_utn
npm install
npm run dev
```

- Crear un archivo `.env` basado en `.env.example`.  
- Configurar `MONGODB_URI`, `JWT_SECRET`, claves de **Resend**, etc.  

Abrir: `http://localhost:3000/` y consumir los endpoints desde el frontend o herramientas como Postman/Bruno.

---

## 🎥 Video Demostrativo

Una vez que tengas el video grabado (YouTube, Drive, etc.), podés incrustarlo acá.

### 👉 Opción 1: Enlace + preview

```md
## 🎥 Video Demostrativo

[Ver video de demostración en YouTube](https://youtube.com/XXXXXXXXX)
```

### 👉 Opción 2: iframe embebido (algunos viewers lo soportan)

> ⚠️ GitHub suele bloquear iframes por seguridad, pero si usás otro visor de Markdown (portfolio personal, Notion, etc.), este bloque funciona:

```html
<div align="center">
  <iframe
    width="800"
    height="450"
    src="https://www.youtube.com/embed/VIDEO_ID"
    title="Demo ShopLink"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen
  ></iframe>
</div>
```

Solo reemplazá `VIDEO_ID` por el código del video de YouTube.

---

## ✅ Estado del Trabajo Práctico

- ✔️ Estructura MVC en backend  
- ✔️ Scripts de desarrollo, build y start configurados  
- ✔️ Logger + rate limiting en rutas de autenticación fileciteturn28file0  
- ✔️ Validación de inputs con Zod  
- ✔️ Uso de variables de entorno (.env + .env.example)  
- ✔️ Deploy del backend en Render y frontend en Vercel  
- ✔️ Subida de archivos (imágenes de productos)  
- ✔️ Envío de correos con Resend  
- ✔️ Documentación en READMEs separados (frontend, backend e integrador)  

---

## 🙌 Agradecimientos

Gracias a los docentes y a la UTN por la guía y el marco del trabajo práctico, y a quienes revisen este repositorio por tomarse el tiempo de ver el proyecto.

Si querés dar feedback, abrir issues o proponer mejoras, ¡más que bienvenido! 🚀
