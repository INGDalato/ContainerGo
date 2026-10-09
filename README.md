# Demo TUDOBENN: app y panel admin (prototipo v4)

Dos códigos independientes que comparten los mismos datos de demostración:

- `index.html`: **app de cliente y conductor** (marco de celular, se cambia de rol en la barra superior).
- `admin.html`: **plataforma web del admin** (panel de escritorio).

Los dos viven en el mismo sitio. Cuando se abren en el **mismo navegador**, comparten el estado (se guarda en el navegador) y se actualizan solos: lo que el cliente solicita aparece en el admin, y lo que el admin aprueba aparece en la app del conductor.

## Montarlo en GitHub Pages (5 minutos)

1. En github.com crea un repositorio público, por ejemplo `tudobenn-demo`.
2. **Add file → Upload files**, sube `index.html` y `admin.html` (con esos nombres exactos) y toca **Commit changes**.
3. **Settings → Pages**: *Deploy from a branch*, rama **main**, carpeta **/ (root)**. Guarda.
4. En 1 o 2 minutos quedan listos:
   - App: `https://TU-USUARIO.github.io/tudobenn-demo/`
   - Admin: `https://TU-USUARIO.github.io/tudobenn-demo/admin.html`

Para actualizar, vuelve a subir los archivos con el mismo nombre.

## Cómo probarlo (dos pestañas del mismo navegador)

Abre la app en una pestaña y el admin en otra (la app tiene un enlace “Abrir panel admin”). Código SMS de prueba: **123456**.

1. **App, cliente**: *Nueva solicitud*, *Ver ofertas*, elige una y paga.
2. **Admin**: *Solicitudes*, abre la solicitud y completa los 4 pasos; aprueba.
3. **App, conductor** (cambia con la barra superior): acepta el servicio, *Simular llegada al punto*, selfie y confirma llegada.
4. **Admin**: *Viajes*, *Enviar PIN de retiro por SMS*.
5. **App, conductor**: PIN de retiro, contenedor, precinto y foto; iniciar tránsito, simular llegada, PIN de entrega (lo ve el cliente en su seguimiento), devolver el vacío.
6. Prueba los botones de emergencia, desvío, parada y GPS sin señal, y mira *Alertas* en el admin.

*Reiniciar demo* (en cualquiera de las dos) borra todo y vuelve al inicio.

## Limitaciones

- La sincronización funciona solo entre pestañas del mismo navegador y del mismo dispositivo. Dos personas en dos equipos no se ven entre sí; para eso hace falta el backend (Supabase), que es la siguiente etapa.
- La simulación de movimiento corre en la pestaña de la app: mantenla abierta mientras pruebas.
- Mapa, GPS, pagos, SMS, llamadas y selfie son simulados. Tarifas, seguros, comisión (10 %), cancelación (20 %), espera y coordenadas son valores de demostración.
- El cierre nocturno de la vía Buga–Buenaventura (8 p. m. a 6 a. m.) es un supuesto de Analdex por confirmar.
- Nombre de marca: en ambos archivos busca `const BRAND='TUDOBENN'` y edita esa línea.
