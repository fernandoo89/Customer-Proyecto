# PeruStyle ----G8

**Plataforma web para la personalización y confección de prendas a pedido en Trujillo, Perú**

PeruStyle es una aplicación web que conecta clientes con confeccionistas especializados en moda peruana. Los usuarios pueden diseñar prendas personalizadas en 3D, enviarlas a confeccionistas verificados, y gestionar todo el proceso de producción desde el pago hasta la entrega.

---

## ✨ Características Principales

### Para Clientes
- 🎨 **Diseñador 3D Interactivo**: Crea diseños personalizados de prendas con vista previa en tiempo real
- 👔 **Marketplace de Confeccionistas**: Explora perfiles de confeccionistas con portafolios y calificaciones
- 💬 **Chat en Tiempo Real**: Comunícate directamente con los confeccionistas
- 💰 **Sistema de Pago Escrow**: Pagos seguros en dos partes (50% adelanto, 50% al finalizar)
- ⭐ **Sistema de Calificaciones**: Califica y comenta el servicio recibido
- 📦 **Seguimiento de Pedidos**: Visualiza el progreso de tus pedidos con actualizaciones en tiempo real

### Para Confeccionistas
- 📋 **Gestión de Pedidos**: Administra cotizaciones, pedidos activos y completados
- 📸 **Subida de Avances**: Comparte fotos y actualizaciones del proceso de confección
- 💼 **Portafolio**: Muestra tus trabajos anteriores a potenciales clientes
- 📊 **Dashboard**: Visualiza estadísticas de ventas y pedidos
- ⭐ **Reputación**: Construye tu reputación con calificaciones de clientes

---

## 🛠️ Tecnologías Utilizadas

### Frontend
- **Vanilla JavaScript** - Lógica de la aplicación
- **Vite** - Build tool y dev server
- **Tailwind CSS** - Framework de estilos
- **Material Symbols** - Iconografía

### Backend
- **Supabase** - Backend as a Service
  - PostgreSQL - Base de datos
  - Authentication - Sistema de autenticación
  - Storage - Almacenamiento de archivos
  - Realtime - Actualizaciones en tiempo real

### Deployment
- **Vercel** - Hosting y CI/CD automático
- **GitHub** - Control de versiones

### Otros
- **PayPal SDK** - Integración de pagos (simulado)
- **Three.js** - Visualización 3D (futuro)

---

## 📋 Requisitos Previos

- Node.js v18 o superior
- npm o yarn
- Cuenta de Supabase (gratuita)
- Cuenta de Vercel (opcional, para deployment)

---

## 🚀 Instalación y Configuración

### 1. Clonar el Repositorio

```bash
git clone https://github.com/franciscoam2328/PeruStyle.git
cd PeruStyle
```

### 2. Instalar Dependencias

```bash
npm install
```

### 3. Configurar Variables de Entorno

Crea un archivo `.env` en la raíz del proyecto:

```env
VITE_SUPABASE_URL=tu_supabase_url
VITE_SUPABASE_ANON_KEY=tu_supabase_anon_key
```

### 4. Configurar Supabase

#### a) Crear Proyecto en Supabase
1. Ve a [supabase.com](https://supabase.com)
2. Crea un nuevo proyecto
3. Copia la URL y la Anon Key

#### b) Ejecutar el Schema SQL
1. Ve a SQL Editor en tu proyecto de Supabase
2. Copia y ejecuta el contenido de `supabase/schema.sql`

#### c) Configurar Storage Buckets
Los buckets se crean automáticamente con el schema, pero verifica que existan:
- `avatars` - Fotos de perfil
- `designs` - Previews de diseños
- `chat-images` - Imágenes del chat

### 5. Ejecutar en Desarrollo

```bash
npm run dev
```

La aplicación estará disponible en `http://localhost:5173`

---

## 📁 Estructura del Proyecto

```
PeruStyle/
├── src/
│   ├── components/          # Componentes reutilizables
│   │   └── logo.js         # Logo de la aplicación
│   ├── js/                 # Lógica de negocio
│   │   ├── auth.js         # Autenticación
│   │   ├── router.js       # Sistema de rutas
│   │   └── supabase.js     # Cliente de Supabase
│   ├── pages/              # Páginas de la aplicación
│   │   ├── home.js         # Landing page
│   │   ├── login.js        # Login/Registro
│   │   ├── client-dashboard.js
│   │   ├── maker-dashboard.js
│   │   ├── orders.js       # Gestión de pedidos (cliente)
│   │   ├── maker-orders.js # Gestión de pedidos (maker)
│   │   ├── chat.js         # Chat en tiempo real
│   │   ├── profile.js      # Perfil de usuario
│   │   ├── maker-profile.js
│   │   ├── my-designs.js   # Diseños del cliente
│   │   ├── design-tool.js  # Herramienta de diseño 3D
│   │   └── ...
│   ├── styles/             # Estilos globales
│   │   └── index.css       # Tailwind + custom styles
│   ├── main.js             # Punto de entrada
│   └── index.html          # HTML principal
├── supabase/
│   └── schema.sql          # Schema de base de datos
├── public/                 # Archivos estáticos
├── .env                    # Variables de entorno (no incluido)
├── .gitignore
├── package.json
├── tailwind.config.js
├── vite.config.js
└── README.md
```

---

## 👥 Roles de Usuario

### Cliente
- Diseñar prendas personalizadas
- Enviar diseños a confeccionistas
- Gestionar pedidos y pagos
- Chatear con confeccionistas
- Calificar servicios recibidos

### Confeccionista (Maker)
- Recibir y cotizar pedidos
- Subir avances del trabajo
- Gestionar portafolio
- Chatear con clientes
- Recibir calificaciones

---

## 🔄 Flujo de Trabajo Principal

1. **Diseño**: El cliente crea un diseño personalizado usando la herramienta 3D
2. **Envío**: El cliente envía el diseño a un confeccionista específico
3. **Cotización**: El confeccionista revisa y establece un precio
4. **Adelanto**: El cliente paga el 50% de adelanto (escrow)
5. **Producción**: El confeccionista trabaja y sube fotos de avances
6. **Entrega Final**: El confeccionista marca el pedido como listo
7. **Pago Final**: El cliente paga el 50% restante
8. **Calificación**: El cliente califica el servicio (1-5 estrellas + comentario)

---

## 📜 Scripts Disponibles

```bash
# Desarrollo
npm run dev          # Inicia servidor de desarrollo en localhost:5173

# Producción
npm run build        # Genera build optimizado en /dist
npm run preview      # Preview del build de producción

# Otros
npm start            # Alias para npm run dev
```

---

## 🚀 Deployment

### Vercel (Recomendado)

1. Conecta tu repositorio de GitHub a Vercel
2. Configura las variables de entorno:
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_ANON_KEY`
3. Vercel detectará automáticamente Vite y configurará el build
4. Cada push a `main` desplegará automáticamente

### Manual

```bash
npm run build
# Sube el contenido de /dist a tu hosting
```

---

## 🗄️ Base de Datos

### Tablas Principales

- **profiles** - Información de usuarios (clientes y makers)
- **designs** - Diseños creados por clientes
- **orders** - Pedidos entre clientes y makers
- **order_updates** - Avances subidos por makers
- **messages** - Mensajes del chat
- **ratings** - Calificaciones de servicios
- **portfolio** - Trabajos de los confeccionistas

### Row Level Security (RLS)

Todas las tablas tienen políticas RLS configuradas para garantizar que:
- Los usuarios solo vean sus propios datos
- Los makers vean pedidos asignados a ellos
- Las calificaciones sean públicas
- Los mensajes solo sean visibles para emisor y receptor

---

## 🎨 Sistema de Diseño

### Paleta de Colores

```css
--primary: #D4AF37      /* Dorado */
--secondary: #C9A961    /* Dorado claro */
--base: #0A0A0A         /* Negro base */
--surface: #1A1A1A      /* Superficie */
--on-surface: #FFFFFF   /* Texto sobre superficie */
```

### Componentes Reutilizables

- Logo (`components/logo.js`)
- Sidebar (integrado en cada página)
- Modales (PayPal, Rating)
- Cards de diseños y pedidos

---

## 🔐 Seguridad

- Autenticación mediante Supabase Auth
- Row Level Security en todas las tablas
- Validación de datos en cliente y servidor
- Sanitización de inputs
- HTTPS en producción (Vercel)

---

## 🐛 Problemas Conocidos

- El sistema de pagos es simulado (no procesa pagos reales)
- El diseñador 3D está en desarrollo inicial
- Algunas imágenes de placeholder necesitan ser reemplazadas

---

## 🤝 Contribución

Las contribuciones son bienvenidas. Por favor:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

---

## 👨‍💻 Autor

- Fernando Benites Mendoza 





- **Supabase**, por tener documentación tan clara que hasta nos sentimos expertos.  
- **Tailwind CSS**, por permitir que una interfaz decente salga incluso cuando el diseñador del grupo está durmiendo.  
- **Vercel**, por ese hosting gratuito que siempre cae como bendición estudiantil.  
---
