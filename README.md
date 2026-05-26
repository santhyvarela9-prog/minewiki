# MineWiki - Wiki Segura de Minecraft

## 🔒 Características de Seguridad Implementadas

### 1. **Protección contra XSS (Cross-Site Scripting)**
- ✅ Sanitización de todas las entradas de usuario con DOMPurify
- ✅ Validación de datos en el cliente y servidor
- ✅ Content Security Policy (CSP) configurado
- ✅ Escape automático de caracteres peligrosos

### 2. **Validación y Whitelist**
- ✅ Búsqueda limitada a 50 caracteres
- ✅ Solo caracteres alfanuméricos permitidos
- ✅ Regex validation en todas las entradas
- ✅ Prevención de inyección de código

### 3. **Rate Limiting**
- ✅ Máximo 100 solicitudes por IP cada 15 minutos
- ✅ Prevención de ataques de fuerza bruta
- ✅ Monitoreo por dirección IP

### 4. **Headers de Seguridad**
- ✅ X-Content-Type-Options: nosniff
- ✅ X-Frame-Options: SAMEORIGIN
- ✅ X-XSS-Protection: 1; mode=block
- ✅ Strict-Transport-Security
- ✅ Permissions-Policy restrictivo

### 5. **Protección de Contenido**
- ✅ Solo el propietario puede modificar
- ✅ Sistema de tokens JWT
- ✅ Autenticación en endpoints admin
- ✅ Logging de cambios

### 6. **SEO Optimizado**
- ✅ Meta tags configurados
- ✅ Open Graph tags
- ✅ Canonical URLs
- ✅ Schema markup listo

## 📋 Archivos Incluidos

- `package.json` - Dependencias necesarias
- `.env.local` - Variables de entorno (NUNCA compartir)
- `.gitignore` - Archivos ignorados en Git
- `lib/security.js` - Funciones de seguridad
- `pages/api/search.js` - API de búsqueda segura
- `pages/index.js` - Página principal
- `pages/_document.js` - Configuración global
- `pages/_app.js` - App wrapper
- `styles/globals.css` - Estilos globales
- `tailwind.config.js` - Configuración de Tailwind
- `next.config.js` - Configuración de Next.js

## 🚀 Instalación

```bash
# Instalar dependencias
npm install

# Configurar variables de entorno
# Editar .env.local con tus valores
nano .env.local

# Ejecutar en desarrollo
npm run dev

# Build para producción
npm run build
npm start
```

## ⚙️ Configuración Requerida

Editar `.env.local`:

```env
NEXT_PUBLIC_SITE_URL=https://tudominio.com
ADMIN_USERNAME=tu_usuario_admin
ADMIN_PASSWORD_HASH=hash_de_tu_password
JWT_SECRET=tu_secret_super_largo_aleatorio
ENCRYPTION_KEY=tu_key_32_caracteres
```

### Generar contraseña hash:
```bash
node -e \"require('bcryptjs').hash('tu_password', 10).then(console.log)\"
```

### Generar JWT secret:
```bash
node -e \"console.log(require('crypto').randomBytes(32).toString('hex'))\"
```

## 📊 API Endpoints

### GET `/api/search?q=diamante`
Búsqueda segura de bloques con validación y rate limiting

**Response:**
```json
{
  \"success\": true,
  \"query\": \"diamante\",
  \"results\": [...],
  \"count\": 1
}
```

## 🛡️ Mejores Prácticas

1. **Nunca** compartas `.env.local`
2. **Siempre** usa HTTPS en producción
3. **Cambia** las credenciales default
4. **Actualiza** dependencias regularmente
5. **Ejecuta** `npm audit` periódicamente
6. **Monitorea** los logs del servidor
7. **Respald** a tu contenido regularmente

## 🔐 Como Propietario

Solo tú puedes:
- Modificar contenido (con autenticación)
- Agregar/eliminar bloques
- Actualizar guías
- Cambiar configuración

El código está protegido contra:
- ✅ XSS attacks
- ✅ Inyección de SQL
- ✅ CSRF attacks
- ✅ Fuerza bruta
- ✅ Modificaciones no autorizadas
- ✅ Scrapers automatizados

## 📝 Licencia

Proyecto privado © 2024 MineWiki

## ⚠️ Disclaimer

No afiliado oficialmente a Minecraft o Mojang Studios.
Proyecto educativo hecho por y para fans de Minecraft.
