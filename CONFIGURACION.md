# Uwork PWA + notificaciones — paquete corregido

## Qué incluye
- `index.html`: aplicación Uwork, pantalla animada, registro del service worker y activación de notificaciones push.
- `manifest.webmanifest` e `icons/`: instalación como PWA.
- `sw.js`: caché de la app y recepción/click de notificaciones.
- `supabase/push_subscriptions.sql`: tabla de suscripciones con RLS.
- `supabase/functions/send-push/index.ts`: código de referencia de la función de envío.
- `VAPID_PUBLIC_KEY.txt`: clave pública configurada en el HTML.

## IMPORTANTE: claves
Este paquete usa la clave pública que ya indicaste que cargaste en Supabase:
`BO13J0SV-ZZY1O7iJ_YPC1CpX-qdQ4a-2hZXncIBotkWPm2nulQ6Z_MbWrPw-1_d9Ucl0iOZAu_Btg3i6zIwqvE`

No cambies ni regeneres los secretos de Supabase. La clave privada nunca debe incluirse en el ZIP público, en Vercel ni en el HTML. En Supabase deben permanecer las claves que ya configuraste y el asunto `mailto:Rincionelucas0@gmail.com`.

## Publicación
Subí el contenido de esta carpeta a la raíz del proyecto Vercel, no el ZIP como archivo. Conservá las rutas: `index.html`, `sw.js`, `manifest.webmanifest`, `icons/`.

## Qué está y qué no está confirmado
El paquete contiene el código de registro de la suscripción y recepción de notificaciones. No se ha confirmado todavía una entrega real en un teléfono. Para verificarlo hay que publicar por HTTPS, iniciar sesión, activar notificaciones desde Uwork y enviar una prueba con la sesión autenticada.

Los eventos reales de negocio (por ejemplo, nueva postulación, mensaje o cambio de estado) deben conectarse desde un backend confiable; este paquete por sí solo no demuestra que esos eventos ya envíen notificaciones.

## Compatibilidad
- Android: Chrome reciente, HTTPS y permiso de notificaciones.
- iPhone/iPad: iOS/iPadOS 16.4 o posterior; añadir Uwork a la pantalla de inicio y abrirla desde ese icono.


REVISIÓN DE UX (30/10/2026): se agregó un bloque visible de instalación y activación de notificaciones en la portada; el aviso de instalación explica los pasos manuales cuando el navegador no ofrece beforeinstallprompt (por ejemplo iPhone/Safari). La pantalla inicial ahora es más compacta y breve. Las notificaciones push requieren iniciar sesión y aceptar el permiso explícitamente.


REVISIÓN VISUAL MÓVIL: se refinó la animación de entrada para usar primero el ícono UW y luego la marca Uwork, con brillo verde sutil, texto de apoyo y barra de progreso corta. En pantallas de hasta 680px, las tarjetas de instalación/notificaciones tienen menos padding, iconos más chicos, texto compacto y botones más bajos. El diseño de escritorio queda sin cambios.
