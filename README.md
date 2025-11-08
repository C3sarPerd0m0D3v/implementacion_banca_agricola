
# README.md

#  Banco de Agricultura - Sistema Bancario Frontend

Sistema de gestión bancaria desarrollado con React + Vite + Material UI.

##  Requisitos Previos

- Node.js 18+ 
- npm o yarn
- Backend Java Spring Boot corriendo en `http://localhost:8080`

##  Instalación

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
o
doble click en 'iniciar_servidor.bat' (ejecutable dentro de  la carpeta del proyecto)

\`\`\`

El proyecto estará disponible en `http://localhost:3000`

##  Estructura del Proyecto

\`\`\`
banco-agricultura-frontend/
├── public/              # Archivos estáticos (logos, imágenes)
├── src/
│   ├── api/            # Configuración de API y llamadas al backend
│   │   ├── axios.config.js      # Configuración base de Axios
│   │   ├── endpoints.js         # Todos los endpoints del backend
│   │   └── hooks/              # Custom Hooks para cada módulo
│   │       ├── useUsuarios.js       # ✅ COMPLETO (Contrato)
│   │       ├── useSucursales.js     # 🔌 Pendiente
│   │       ├── useCuentas.js        # ✅ COMPLETO (Contrato)
│   │       ├── usePrestamos.js      # ✅ COMPLETO (Contrato)
│   │       ├── useMovimientos.js    # ✅ COMPLETO (Contrato)
│   │       ├── useTransferencias.js # ✅ COMPLETO (Contrato)
│   │       └── useTokenTransaccion.js # ✅ COMPLETO (Contrato)
│   │
│   ├── pages/          # Páginas de la aplicación
│   │   ├── usuarios/
│   │   │   ├── ListaUsuarios.jsx       # ✅ COMPLETO
│   │   │   └── FormularioUsuario.jsx   # ✅ COMPLETO
│   │   ├── sucursales/    #  🔌 Pendiente
│   │   ├── cuentas/       # ✅ COMPLETO
│   │   ├── prestamos/     # ✅ COMPLETO
│   │   ├── movimientos/   # ✅ COMPLETO
│   │   ├── transferencias/ # ✅ COMPLETO
│   │   └── dependientes/  #  🔌 Pendiente
│   │
│   ├── utils/          # Funciones de utilidad
│   │   └── formatters.js    # Formateo de fechas, moneda, DUI, teléfono
│   │
│   ├── App.jsx         # Componente principal con routing
│   └── main.jsx        # Punto de entrada
│
├── vite.config.js      # Configuración de Vite
├── package.json        # Dependencias del proyecto
└── README.md           # Este archivo
\`\`\`

##  Tecnologías

- **React 18.3.1** - Librería UI
- **Vite 5.4** - Build tool
- **Material UI v6** - Framework de componentes
- **React Router 6.26** - Routing
- **Axios 1.6** - Cliente HTTP
- **React Hook Form 7.53** - Manejo de formularios
- **Zod 3.23** - Validación de esquemas

##  Credenciales de Prueba

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

## Modulos del Sistema

✅ Modulos Implementados (endpoints definidos)
1. **Autenticacion**
✅ Login con validacion 

✅ Manejo de sesión (Context) 

✅ Logout 

✅ Protección de rutas (implicita en App.jsx )

2. **Dashboard**
✅ Menu desplegable y navegación 

✅ Diseño responsivo

3. **Gestión de Usuarios**
✅ Lista de usuarios con búsqueda 

✅ Crear/Editar/Eliminar usuario (simulado) 

✅ Formulario con validación Zod (DUI, Teléfono, etc.) 

✅ Indicadores visuales de rol y estado 

4. **Servicios - Cuentas**
✅ Lista de cuentas bancarias (Mock)

✅ Formulario para solicitar cuenta (Ahorro/Corriente) con validación

✅ Lógica para cambiar estado (simulada)

5. **Servicios - Préstamos**
✅ Lista de préstamos (Mock)

✅ Formulario para solicitar préstamo con validación

✅ Lógica para Aprobar/Rechazar (simulada)

6. **Servicios - Movimientos**
✅ Hook para leer historial de una cuenta (Mock)

✅ Componente de vista de historial (usado en modal de Cuentas)

7. **Servicios - Transferencias**
✅ Formulario para Transferencia Normal (cuenta a cuenta)

✅ Formulario para Transferencia Express (generar token)

✅ Lista de tokens activos (Mock)

✅ Validación Zod para ambos formularios

🔌 Módulos Pendientes (con estructura preparada)

8. **Gestion de Sucursales**
🔌 Lista de sucursales

🔌 Crear/Editar sucursal

🔌 Campos: Nombre, Dirección, Teléfono, Ciudad, Estado

9. **Dependientes**
🔌 Consultar dependientes

🔌 Agregar dependiente

🔌 Lista de dependientes por usuario

10. **Gestiones**
🔌 Gestionar cuentas (reportes, estados)

🔌 Gestionar préstamos (análisis, aprobaciones masivas)


##  Integración con Backend

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

### Formato de Respuesta del backend esperado

\`\`\`json
{
  "success": true,
  "data": {
    "id": 1,
    "nombre": "banne",
    "email": "banne@banco.com"
  },
  "message": "Operacion exitosa"
}

### Formato para errores

{
  "success": false,
  "data": null,
  "message": "Error al procesar la solicitud",
  "errors": {
    "email": ["El email ya esta registrado"],
    "dui": ["Formato de DUI invalido"]
  }
}

\`\`\`

### Headers Requeridos

\`\`\`
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json
Accept: application/json
\`\`\`

##  Scripts Disponibles

\`\`\`bash
npm run dev       # Iniciar servidor de desarrollo
npm run build     # Construir para producción
npm run preview   # Vista previa de producción
npm run lint      # Ejecutar ESLint
\`\`\`

##  Funcionalidades Principales

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

##  Sistema de Roles

- **ADMIN**: Acceso completo al sistema
- **EMPLEADO**: Gestión de cuentas, préstamos y clientes
- **CLIENTE**: Solo consulta de sus propios datos

##  Personalización

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

##  Responsive Design

La aplicación está optimizada para:
-  Mobile (< 600px)
-  Tablet (600px - 960px)
-  Desktop (> 960px)

##  Solución de Problemas

### Error de CORS
Verificar que el backend tenga CORS habilitado para `http://localhost:3000`

### Token Expirado
El sistema redirige automáticamente al login cuando el token expira (error 401)

### Proxy no funciona
Verificar configuración en `vite.config.js` y que el backend esté corriendo en puerto 8080

##  Recursos

- [React Docs](https://react.dev)
- [Material UI](https://mui.com)
- [React Router](https://reactrouter.com)
- [Axios](https://axios-http.com)
- [React Hook Form](https://react-hook-form.com)

##  Equipo

Desarrollado para facilitar la integración con el backend Java Spring Boot.


---

**Nota para el equipo de Backend:**
Todos los endpoints están documentados en `src/api/endpoints.js`. Los formatos de request/response esperados están comentados en cada custom hook (`src/api/hooks/`).

Endpoints del Backend (Todos documentados en src/api/endpoints.js)
Autenticación
POST /api/auth/login

POST /api/auth/logout

GET /api/auth/me

Usuarios
GET /api/usuarios

POST /api/usuarios

GET /api/usuarios/:id

PUT /api/usuarios/:id

DELETE /api/usuarios/:id

GET /api/usuarios/buscar?dui=12345678-9

POST /api/usuarios/cambiar-password

Sucursales
GET /api/sucursales

POST /api/sucursales

PUT /api/sucursales/:id

DELETE /api/sucursales/:id

Cuentas
GET /api/cuentas

POST /api/cuentas

GET /api/cuentas/usuario/:usuarioId

PUT /api/cuentas/:id

DELETE /api/cuentas/:id

Préstamos
GET /api/prestamos

POST /api/prestamos

POST /api/prestamos/:id/aprobar

POST /api/prestamos/:id/rechazar

GET /api/prestamos/usuario/:usuarioId

Transferencias
GET /api/transferencias

POST /api/transferencias

POST /api/transferencias/express

GET /api/transferencias/historial

Dependientes
GET /api/dependientes

POST /api/dependientes

GET /api/dependientes/usuario/:usuarioId

PUT /api/dependientes/:id

DELETE /api/dependientes/:id

Reportes
GET /api/reportes/dashboard



=======
