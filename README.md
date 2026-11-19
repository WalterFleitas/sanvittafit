# Sanvitta Fit · Pedidos

Página de pedidos de marmitas. El cliente elige por día y envía el pedido por WhatsApp. En `#panel` (enlace al pie de la página) Sthefany pega el mensaje recibido y ve pedidos, qué cocinar y comandas para imprimir.

Es un solo archivo, `index.html`. No necesita instalación ni compilación.

## Publicar (GitHub + Netlify)

1. Crear un repositorio en GitHub (por ejemplo `sanvitta-fit`) y subir `index.html` y este `README.md`.
2. En Netlify: **Add new site → Import an existing project**, conectar GitHub y elegir el repositorio.
3. Dejar vacío el comando de compilación y usar la raíz como carpeta a publicar. Pulsar **Deploy**.
4. Cambiar el nombre del sitio en **Site configuration → Change site name** (ej. `sanvitta-fit`).

Desde ahí, cada cambio guardado en GitHub se publica solo en un minuto.

## Cambiar el menú, los precios o el número

Abrir `index.html` en GitHub (ícono del lápiz) y buscar estas líneas, que están juntas dentro del `<script>`:

- `const WA_NUMBER` → número de WhatsApp que recibe los pedidos, con código de país y sin signos. Ejemplo: `5597991452556`.
- `const MENU` → un bloque por día con `day`, `dish` y `fish`.
  - `dish` es el texto del plato.
  - `fish: true` marca el día de tilapia, que se cobra aparte.
- `const PRICE` → `single` (marmita), `fish` (tilapia) y `packs` (cantidad y precio de cada pack).

Los packs que salen más caros que comprar sueltas no se muestran ni se aplican.

Guardar con **Commit changes**. Netlify publica la nueva versión sola.

## Importante

- Los pedidos del panel se guardan solo en el navegador del dispositivo donde se cargan. Usar siempre el mismo celular o computadora para el panel.
- Si el menú cambia, avisar a los clientes para que recarguen la página.
