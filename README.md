# Mi economía personal

Aplicación web estática instalable (PWA). No usa ChatGPT, IA, cuentas externas, analítica ni servicios de terceros. Los datos financieros se guardan en IndexedDB del dispositivo. La primera vez, completa los datos desde la pantalla de configuración; el paquete no trae saldos, deudas ni movimientos personales precargados.

## Archivos

- `index.html`: aplicación, estilos y funciones.
- `manifest.json`: nombre, colores e iconos de instalación.
- `sw.js`: guarda la pantalla y los recursos para abrirlos sin conexión.
- `icons/`: iconos locales de la app para Safari y el sistema.

## Publicar en GitHub Pages desde iPad

1. Descarga el ZIP y tócala en **Archivos** para descomprimirlo.
2. En Safari, inicia sesión en GitHub y crea un repositorio nuevo para la app. En GitHub Free, el sitio Pages de una cuenta personal debe estar en un repositorio público.
3. En el repositorio, usa **Add file → Upload files** y carga `index.html`, `manifest.json` y `sw.js` en la raíz. Crea la carpeta `icons` con **Add file → Create new file**, escribe `icons/.keep`, confirma el archivo y luego abre esa carpeta y carga los dos PNG. El archivo `.keep` puede quedarse allí.
4. Confirma los cambios con **Commit changes**.
5. En el repositorio abre **Settings → Pages**. En **Build and deployment**, elige publicar desde una rama, selecciona `main` y `/ (root)`, y guarda.
6. Espera a que GitHub Pages indique que publicó el sitio. Abre la dirección `https://TU-USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/` en Safari.
7. Deja que cargue y vuelve a cargar una vez con internet para que el Service Worker guarde los archivos de la app. Configura tus datos desde la aplicación.

**Privacidad:** GitHub Pages publica los archivos del sitio. Este paquete no contiene tus datos, pero no subas copias de seguridad, exportaciones CSV ni archivos con información financiera al repositorio. Cada dispositivo conserva su propia base local; para pasar los datos a otro dispositivo usa la copia cifrada.

## Instalar en iPhone o iPad

1. Abre la dirección publicada en **Safari** y espera a que cargue completamente con internet.
2. Toca **Compartir**.
3. Elige **Agregar a pantalla de inicio**. Si no aparece, desplázate a **Editar acciones** y agrégala.
4. Activa **Abrir como app web** si aparece la opción y toca **Agregar**.
5. Abre el icono desde la pantalla de inicio. Tras la primera carga y el almacenamiento del Service Worker, prueba el modo avión.

## Prueba sin conexión

1. Con internet, abre la dirección, espera a que cargue y vuelve a cargar una vez.
2. Cierra Safari y activa el modo avión.
3. Abre **Mi economía personal** desde su icono. Debe mostrar la app y conservar los datos de ese dispositivo.
4. Registra una transferencia, un gasto y un retiro. Cierra y vuelve a abrir la app para comprobar que los datos siguen allí.
5. Desactiva el modo avión al terminar.

## Alcance y límites

- La app no sincroniza entre dispositivos. Cada navegador o instalación tiene su propio IndexedDB.
- Safari o el usuario pueden borrar el almacenamiento del sitio. Guarda una copia cifrada periódicamente.
- La impresión a PDF usa la hoja de compartir/impresión del sistema; no requiere librerías externas.
- La publicación es pública en internet. La contraseña de una copia protege ese archivo, no el HTML publicado.

## Referencias oficiales

- [Crear un sitio de GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Agregar un sitio a la pantalla de inicio del iPad](https://support.apple.com/guide/ipad/bookmark-a-website-ipadc602b75b/27/ipados/27)
- [Agregar un sitio web como app en iPhone](https://support.apple.com/guide/iphone/open-as-web-app-iphea86e5236/27/ios/27)
