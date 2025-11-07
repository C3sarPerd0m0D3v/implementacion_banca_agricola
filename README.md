# README.md

# 🏦 Banco de Agricultura - Sistema Bancario Frontend

Sistema de gestión bancaria desarrollado con React + Vite + Material UI.

## 📋 Requisitos Previos

- Node.js 18+ 
- npm o yarn
- Backend Java Spring Boot corriendo en `http://localhost:8080`

## 🚀 Instalación

\`\`\`bash
# Clonar repositorio
git clone <repo-url>
cd banco-agricultura-frontend

# Instalar dependencias
npm install

# Configurar variables de entorno
cp .env.example .env
# Editar .env con tus configuraciones

# Iniciar servidor de desarrollo
npm run dev
\`\`\`

El proyecto estará disponible en `http://localhost:3000`

## 📁 Estructura del Proyecto

\`\`\`
src/
├── api/              # Configuración Axios y Custom Hooks
├── app/              # Routing y ProtectedRoute
├── components/       # Componentes reutilizables
│   ├── common/       # Componentes comunes
│   ├── forms/        # Componentes de formularios
│   └── layout/       # Layout principal
├── context/          # Context API (Auth, Theme)
├── pages/            # Páginas de la aplicación
│   ├── auth/         # Login
│   ├── dashboard/    # Dashboard
│   ├── cuentas/      # Gestión de cuentas
│   ├── prestamos/    # Gestión de préstamos
│   └── movimientos/  # Transacciones
├── theme/            # Tema Material UI
├── utils/            # Funciones de utilidad
├── App.jsx           # Componente raíz
└── main.jsx          # Punto de entrada
\`\`\`

## 🎨 Tecnologías

- **React 18.3.1** - Librería UI
- **Vite 5.4** - Build tool
- **Material UI v6** - Framework de componentes
- **React Router 6.26** - Routing
- **Axios 1.6** - Cliente HTTP
- **React Hook Form 7.53** - Manejo de formularios
- **Zod 3.23** - Validación de esquemas

## 🔑 Credenciales de Prueba

\`\`\`
Admin:
  Email: admin@banco.com
  Password: admin123

Empleado:
  Email: empleado@banco.com
  Password: emp123

Cliente:
  Email: cliente@banco.com
  Password: cli123
\`\`\`

## 🔗 Integración con Backend

### Endpoints Requeridos

El backend debe implementar los siguientes endpoints:

#### Autenticación
- `POST /api/auth/login` - Login
- `GET /api/auth/me` - Usuario actual

#### Cuentas
- `GET /api/cuentas` - Listar cuentas
- `POST /api/cuentas` - Crear cuenta
- `PUT /api/cuentas/:id` - Actualizar cuenta
- `DELETE /api/cuentas/:id` - Eliminar cuenta

#### Préstamos
- `GET /api/prestamos` - Listar préstamos
- `POST /api/prestamos` - Crear préstamo
- `POST /api/prestamos/:id/aprobar` - Aprobar préstamo
- `POST /api/prestamos/:id/rechazar` - Rechazar préstamo

#### Movimientos
- `GET /api/movimientos` - Listar movimientos
- `POST /api/movimientos` - Crear movimiento

#### Reportes
- `GET /api/reportes/dashboard` - Estadísticas dashboard

### Formato de Response Esperado

\`\`\`json
{
  "success": true,
  "message": "Operación exitosa",
  "data": { ... }
}
\`\`\`

### Headers Requeridos

\`\`\`
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json
\`\`\`

## 🛠️ Scripts Disponibles

\`\`\`bash
npm run dev       # Iniciar servidor de desarrollo
npm run build     # Construir para producción
npm run preview   # Vista previa de producción
npm run lint      # Ejecutar ESLint
\`\`\`

## 🎯 Funcionalidades Principales

### Autenticación
- Login con JWT
- Persistencia de sesión
- Logout
- Protección de rutas

### Dashboard
- Estadísticas generales
- Tarjetas de resumen
- Saludo personalizado

### Gestión de Cuentas
- Listar cuentas
- Crear nueva cuenta
- Editar cuenta
- Eliminar cuenta
- Búsqueda por número/cliente

### Gestión de Préstamos
- Listar préstamos
- Crear préstamo
- Aprobar/Rechazar préstamos
- Filtros por estado

### Movimientos
- Historial de transacciones
- Filtros por fecha
- Indicadores visuales (depósito/retiro)

## 🔐 Sistema de Roles

- **ADMIN**: Acceso completo al sistema
- **EMPLEADO**: Gestión de cuentas, préstamos y clientes
- **CLIENTE**: Solo consulta de sus propios datos

## 🎨 Personalización

### Cambiar Colores del Tema

Editar `src/theme/theme.js`:

\`\`\`javascript
primary: {
  main: '#2E7D32', // Verde del banco
  light: '#60AD5E',
  dark: '#005005'
},
secondary: {
  main: '#FFA726', // Naranja
  light: '#FFD95B',
  dark: '#C77800'
}
\`\`\`

## 📱 Responsive Design

La aplicación está optimizada para:
- 📱 Mobile (< 600px)
- 📱 Tablet (600px - 960px)
- 💻 Desktop (> 960px)

## 🐛 Solución de Problemas

### Error de CORS
Verificar que el backend tenga CORS habilitado para `http://localhost:3000`

### Token Expirado
El sistema redirige automáticamente al login cuando el token expira (error 401)

### Proxy no funciona
Verificar configuración en `vite.config.js` y que el backend esté corriendo en puerto 8080

## 📚 Recursos

- [React Docs](https://react.dev)
- [Material UI](https://mui.com)
- [React Router](https://reactrouter.com)
- [Axios](https://axios-http.com)
- [React Hook Form](https://react-hook-form.com)

## 👥 Equipo

Desarrollado para facilitar la integración con el backend Java Spring Boot.

## 📄 Licencia

MIT

---

**Nota para el equipo de Backend:**
Todos los endpoints están documentados en `src/api/endpoints.js`. Los formatos de request/response esperados están comentados en cada custom hook (`src/api/hooks/`).
\`\`\`

Ahora crearé la **ESTRUCTURA COMPLETA DEL BACKEND** en Java Spring Boot...

## 🔥 ESTRUCTURA BACKEND JAVA SPRING BOOT
