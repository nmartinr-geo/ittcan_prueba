# Publicación de ITTCAN en GitHub Pages

Paquete exportado de Experience Builder 1.21, con las tres instancias del widget 1.1 conectadas a widget_1: territorio, capas e histogramas. La página de comparación se conserva. Los nombres de las tres instancias en el archivo de configuración son correctos. Este paquete no modifica la instalación local ni corrige el nombre de la tarjeta del catálogo local del editor.

## Pendiente antes de usarlo con visitantes

La consulta anónima al mapa devolvió 403 y la tabla territorial devolvió 499 (Token Required). La capa de municipios sí respondió sin sesión. Esto no determina los permisos de todas las capas del mapa. No se han cambiado permisos.

El campo attributes.clientId en cdn/1/config.json está vacío. Si se mantiene el contenido restringido, hay que registrar la URL final en las credenciales OAuth de ArcGIS y completar clientId con el identificador público de la aplicación (nunca el secreto). Los visitantes deberán disponer de permisos sobre los datos. Si el visor será público, el propietario debe compartir los elementos necesarios con Todos y comprobar también todas las capas y tablas relacionadas.

## Subir con GitHub Desktop

1. Crear un repositorio llamado visor-ittcan. Para GitHub Pages con GitHub Free debe ser público.
2. Clonarlo en el ordenador con GitHub Desktop.
3. Copiar TODO el contenido de este paquete dentro de la carpeta del repositorio. index.html, cdn y .nojekyll deben quedar en la raíz, sin una carpeta adicional. No subir el ZIP como único archivo.
4. Hacer Commit y Push desde GitHub Desktop. No subir la instalación C:/ExperienceBuilder ni sus carpetas client/server.
5. En GitHub: Settings > Pages > Deploy from a branch > main > /(root) > Save.
6. La URL será https://USUARIO.github.io/visor-ittcan/. Completar el registro OAuth con esa dirección si hay contenido restringido y añadir el clientId en la configuración.
7. Probar esa URL en ventana de incógnito: comprobar acceso a mapa, capas, estadísticas, cambio de municipio, zoom y sincronización de histogramas.

.nojekyll evita que GitHub procese las carpetas de la aplicación con Jekyll. Se conserva el index.html y toda la estructura exportada. No hay un despliegue realizado todavía, ni prueba funcional en un alojamiento público.

## Actualizaciones

Editar y publicar en Developer Edition, descargar otra vez la experiencia, preparar el nuevo paquete y reemplazar los archivos del mismo repositorio. Conservar .nojekyll y la configuración de acceso. La URL no cambia mientras se mantengan usuario y repositorio. Si se editan directamente archivos de una exportación ya desplegada, hay que actualizar también el número de compilación y su carpeta cdn para invalidar la caché, según la guía de Esri.
