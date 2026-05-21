# 🚀 Guía de Despliegue - RoloTech Website

## Repositorio GitHub
- **URL:** https://github.com/trevinot88/rolotechweb
- **Rama principal:** main

## Dominio Personalizado
- **Dominio:** rolotech.pro

---

## 📋 Pasos para Desplegar en Render

### 1️⃣ Crear Static Site en Render

1. Ve a [Render Dashboard](https://dashboard.render.com/)
2. Click en **"New +"** → Selecciona **"Static Site"**
3. Conecta tu repositorio de GitHub:
   - Click en **"Connect GitHub"** (si aún no lo has hecho)
   - Busca y selecciona el repositorio: `trevinot88/rolotechweb`
   - Click en **"Connect"**

### 2️⃣ Configurar el Static Site

Completa el formulario con estos datos:

- **Name:** `rolotech` (o el nombre que prefieras)
- **Branch:** `main`
- **Root Directory:** (dejar vacío)
- **Build Command:** (dejar vacío - no necesita build)
- **Publish Directory:** `.` (punto, indica la raíz del proyecto)

⚠️ **IMPORTANTE:** Como tu sitio es solo HTML/CSS/JS, NO necesitas comandos de build.

### 3️⃣ Configurar Variables de Entorno (Opcional)

No se requieren variables de entorno para este proyecto.

### 4️⃣ Desplegar

1. Click en **"Create Static Site"**
2. Render comenzará el despliegue automáticamente
3. Espera 2-3 minutos hasta que veas **"Your site is live"**
4. Te dará una URL temporal como: `https://rolotech.onrender.com`

### 5️⃣ Configurar Dominio Personalizado (rolotech.pro)

1. En el Dashboard de tu sitio en Render, ve a la pestaña **"Settings"**
2. Scroll hasta la sección **"Custom Domain"**
3. Click en **"Add Custom Domain"**
4. Ingresa: `rolotech.pro`
5. También agrega: `www.rolotech.pro` (para que funcione con y sin www)

### 6️⃣ Configurar DNS en tu Proveedor de Dominio

Render te mostrará los registros DNS que necesitas configurar. Ve al panel de control de donde compraste el dominio (GoDaddy, Namecheap, etc.) y agrega:

**Para el dominio raíz (rolotech.pro):**
```
Tipo: A
Host: @
Valor: 216.24.57.1 (IP que te proporcione Render)
```

**Para www (www.rolotech.pro):**
```
Tipo: CNAME
Host: www
Valor: rolotech.onrender.com (tu URL de Render)
```

⏰ **Nota:** La propagación DNS puede tardar de 5 minutos a 48 horas.

### 7️⃣ Activar HTTPS (Automático)

- Render activa SSL/HTTPS automáticamente para dominios personalizados
- Una vez configurado el DNS, espera unos minutos
- Tu sitio estará disponible en: `https://rolotech.pro` 🔒

---

## 🔄 Actualizaciones Futuras

Cada vez que hagas cambios y ejecutes:
```bash
git add .
git commit -m "Descripción de cambios"
git push origin main
```

Render detectará los cambios automáticamente y desplegará la nueva versión en 1-2 minutos.

---

## ✅ Verificación

Una vez desplegado, verifica que todo funcione:

- ✅ Página carga correctamente
- ✅ Todas las secciones visibles (Hero, Servicios, Portfolio, etc.)
- ✅ Enlaces de navegación funcionan
- ✅ Botones de WhatsApp redirigen correctamente
- ✅ Formulario de contacto envía a WhatsApp
- ✅ Imágenes cargan correctamente (Unsplash CDN)
- ✅ Fuentes e iconos se ven bien (Google Fonts, Font Awesome)
- ✅ Responsive design funciona en móvil

---

## 🆘 Solución de Problemas

**Si la página no carga:**
- Verifica que el Publish Directory sea `.` (punto)
- Asegúrate de que `index.html` esté en la raíz del repositorio

**Si el dominio no funciona:**
- Verifica la configuración DNS en tu proveedor
- Espera al menos 30 minutos para propagación DNS
- Usa [dnschecker.org](https://dnschecker.org) para verificar la propagación

**Si las imágenes no cargan:**
- Las imágenes usan Unsplash CDN, deberían funcionar automáticamente
- Verifica la consola del navegador (F12) para errores

---

## 📞 Soporte

- Render Docs: https://docs.render.com/static-sites
- Render Community: https://community.render.com/

---

**¡Tu sitio estará en línea en minutos!** 🎉
