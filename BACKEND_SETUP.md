# 🚀 GUÍA DE CONFIGURACIÓN DEL BACKEND

Esta guía te ayudará a configurar paso a paso el backend de tu portfolio.

## 📋 REQUISITOS PREVIOS

- Node.js 18+ instalado
- Cuenta en GitHub
- Editor de código (VS Code recomendado)

## 🗄️ PASO 1: CONFIGURAR BASE DE DATOS

### Opción A: Supabase (Recomendado)

1. **Crear cuenta en Supabase**
   - Ve a [https://supabase.com](https://supabase.com)
   - Crea una cuenta gratuita
   - Crea un nuevo proyecto

2. **Obtener credenciales**
   - Ve a Settings > API
   - Copia la `URL` y `anon key`
   - Pégalas en `.env.local`

3. **Crear tablas**
   - Ve a SQL Editor en Supabase
   - Ejecuta el SQL que está en `lib/database.ts`

### Opción B: Neon (Alternativa)

1. **Crear cuenta en Neon**
   - Ve a [https://neon.tech](https://neon.tech)
   - Crea una cuenta gratuita
   - Crea una nueva base de datos

2. **Obtener connection string**
   - Copia la connection string
   - Pégala como `DATABASE_URL` en `.env.local`

## 📧 PASO 2: CONFIGURAR EMAIL

### Opción A: EmailJS (Más fácil)

1. **Crear cuenta en EmailJS**
   - Ve a [https://emailjs.com](https://emailjs.com)
   - Crea una cuenta gratuita

2. **Configurar servicio de email**
   - Ve a Email Services
   - Conecta tu Gmail, Outlook, etc.
   - Copia el Service ID

3. **Crear plantilla**
   - Ve a Email Templates
   - Crea una nueva plantilla
   - Usa las variables: `{{from_name}}`, `{{from_email}}`, `{{message}}`
   - Copia el Template ID

4. **Obtener Public Key**
   - Ve a Account > General
   - Copia tu Public Key

### Opción B: Resend (Más avanzado)

1. **Crear cuenta en Resend**
   - Ve a [https://resend.com](https://resend.com)
   - Crea una cuenta

2. **Generar API Key**
   - Ve a API Keys
   - Genera una nueva key
   - Pégala en `.env.local`

## 🔧 PASO 3: CONFIGURAR VARIABLES DE ENTORNO

1. **Crear archivo .env.local**
   \`\`\`bash
   cp .env.local.example .env.local
   \`\`\`

2. **Completar variables requeridas**
   - Supabase: `NEXT_PUBLIC_SUPABASE_URL` y `NEXT_PUBLIC_SUPABASE_ANON_KEY`
   - EmailJS: `NEXT_PUBLIC_EMAILJS_SERVICE_ID`, `NEXT_PUBLIC_EMAILJS_TEMPLATE_ID`, `NEXT_PUBLIC_EMAILJS_PUBLIC_KEY`

## 🧪 PASO 4: PROBAR LA CONFIGURACIÓN

1. **Instalar dependencias**
   \`\`\`bash
   npm install @supabase/supabase-js @emailjs/browser
   \`\`\`

2. **Ejecutar en desarrollo**
   \`\`\`bash
   npm run dev
   \`\`\`

3. **Probar formulario de contacto**
   - Ve a la sección de contacto
   - Envía un mensaje de prueba
   - Verifica que llegue a tu email

## 🚀 PASO 5: DESPLEGAR EN PRODUCCIÓN

### Vercel (Recomendado)

1. **Conectar repositorio**
   - Ve a [https://vercel.com](https://vercel.com)
   - Conecta tu repositorio de GitHub

2. **Configurar variables de entorno**
   - Ve a Settings > Environment Variables
   - Agrega todas las variables de `.env.local`

3. **Desplegar**
   - Vercel desplegará automáticamente
   - Actualiza `NEXT_PUBLIC_BASE_URL` con tu dominio

## 🔍 SOLUCIÓN DE PROBLEMAS

### Error: "Variables de entorno faltantes"
- Verifica que todas las variables estén en `.env.local`
- Reinicia el servidor de desarrollo

### Error: "No se puede conectar a Supabase"
- Verifica la URL y clave anon
- Asegúrate de que el proyecto esté activo

### Error: "Email no se envía"
- Verifica las credenciales de EmailJS
- Revisa la consola del navegador para errores

### Error: "CORS en producción"
- Configura los dominios permitidos en Supabase
- Verifica la configuración de EmailJS

## 📚 RECURSOS ADICIONALES

- [Documentación de Supabase](https://supabase.com/docs)
- [Documentación de EmailJS](https://www.emailjs.com/docs/)
- [Documentación de Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)

## 🆘 SOPORTE

Si tienes problemas:
1. Revisa los logs en la consola del navegador
2. Verifica las variables de entorno
3. Consulta la documentación oficial de cada servicio
