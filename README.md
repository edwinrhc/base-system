# 🚀 Base System – NestJS Starter Template con Auth, JWT y Roles

<p align="center">
  <a href="http://nestjs.com/" target="blank">
    <img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo"/>
  </a>
</p>

<p align="center">
  Plantilla inicial para construir aplicaciones backend en <strong>NestJS</strong>, incluyendo:
</p>

<p align="center">
 🔐 Autenticación con JWT · 👤 Registro/Login · 👮 Roles (admin/user) · 🛡️ Guards · 🧭 Dashboard protegido  
</p>

---

## 📌 Descripción

**Base System** es un proyecto monolítico construido con **NestJS**, diseñado como punto de partida para cualquier sistema backend profesional.  
Incluye un módulo completo de autenticación, manejo de roles y un dashboard protegido con JWT.

### Características principales

- ✔️ Registro de usuarios
- ✔️ Login con JWT
- ✔️ Guards para proteger rutas
- ✔️ Roles: `admin` y `user`
- ✔️ Acceso restringido a endpoints
- ✔️ Arquitectura modular
- ✔️ Código limpio y escalable

---

# 📁 Estructura del Proyecto

```txt
src/
 ├── auth/
 │    ├── auth.controller.ts
 │    ├── auth.service.ts
 │    ├── auth.module.ts
 │    ├── guards/
 │    ├── strategies/
 │    └── decorators/
 ├── users/
 │    ├── users.controller.ts
 │    ├── users.service.ts
 │    └── entities/
 ├── dashboard/
 ├── common/
 ├── main.ts
```

---

# 🚀 Instalación

```bash
npm install
```

---

# ▶️ Ejecutar el Proyecto

### Modo desarrollo
```bash
npm run start:dev
```

### Modo normal
```bash
npm run start
```

### Producción
```bash
npm run start:prod
```

---

# 🔐 Endpoints incluidos

## 1. Registro
```
POST /auth/register
```
Body:
```json
{
  "name": "Edwin",
  "email": "edwin@example.com",
  "password": "123456",
  "role": "admin"
}
```

## 2. Login
```
POST /auth/login
```
Respuesta:
```json
{
  "access_token": "token_jwt_here",
  "user": { ... }
}
```

## 3. Dashboard protegido
```
GET /dashboard
Authorization: Bearer <token>
```

## 4. Dashboard solo para ADMIN
```
GET /dashboard/admin
Authorization: Bearer <token_admin>
```

---

# 👮 Roles incluidos

Disponible en `UserRole`:

```ts
export enum UserRole {
  ADMIN = 'admin',
  USER = 'user'
}
```

---

# 🛡️ Seguridad incluida

- JWT Strategy configurada
- `JwtAuthGuard` para proteger rutas
- `RolesGuard` para control de permisos
- Decorador `@Roles('admin')` para rutas especiales

---

# 🧪 Tests básicos

```bash
npm run test
npm run test:e2e
npm run test:cov
```

---

# 📦 Tecnologías utilizadas

- NestJS
- TypeScript
- Passport + JWT
- Bcrypt
- Arquitectura Modular
- Guards, Decorators y Strategies
- Prisma

---


## 🗄️ Configuración de la Base de Datos

En el archivo `.env`:

```env
DATABASE_URL="mysql://root:password@localhost:3306/base_system"
JWT_SECRET="super_secret_key"
JWT_EXPIRES="2h"
````
# 🌐 Futuras mejoras

- Refresh Tokens
- Auditoría (createdBy, updatedBy)
- Permisos avanzados (RBAC)
- Manejo avanzado de errores

---

# 🧑‍💻 Autor

**Edwin RHC**  
Backend Developer · Java · Spring Boot · Node.js · NestJS  
GitHub: https://github.com/edwinrhc

---

# 📄 Licencia

MIT — libre para usar y modificar.
