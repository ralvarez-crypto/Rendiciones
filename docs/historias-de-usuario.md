Historia
Como Operador, quiero dejar los documentos escaneados en la carpeta de entrada y procesarlos desde la aplicación, para no tener que ingresarlos uno por uno.

Propósito
Que el operador pueda procesar las boletas y facturas escaneadas desde la aplicación, sin que los archivos salgan del Drive del grupo de trabajo ni se guarden en el servidor.

Alcance

Carpeta de entrada
Los escaneos se dejan en la carpeta de entrada del Drive del grupo de trabajo.
Procesamiento
El botón "Procesar documentos" solo está disponible con la sesión iniciada.
La aplicación revisa qué archivos hay en la carpeta y les asigna una huella digital a cada uno, que le permite reconocer si ya los procesó antes.
Los archivos que ya fueron procesados se saltan.
Cada documento se descarga de forma temporal y se procesa por separado.
Resumen
Al terminar, la aplicación muestra cuántos documentos se procesaron, cuántos se saltaron por estar repetidos y cuántos dieron error.

Criterios de aceptación

Solo puede procesar documentos un usuario con sesión iniciada, y eso se valida en el servidor.
Un archivo con un hash que ya está registrado no se procesa otra vez.
Si un documento falla, los demás se siguen procesando.
Los archivos temporales se borran apenas se termina con cada documento.
Ningún archivo queda guardado en el disco del servidor ni en la base de datos. Solo se guardan sus datos y su hash.
No se pueden correr dos procesamientos al mismo tiempo, y el botón queda desactivado mientras hay uno en curso.

Resultado esperado
Una pantalla con el botón "Procesar documentos" y el resumen del último procesamiento, conectada a la carpeta de entrada del Drive del grupo de trabajo.

Tareas técnicas


Solicitar el acceso a las carpetas del Drive

Armar el acceso a Drive: listar, descargar y mover archivos

Calcular el hash (huella digital) y guardarlo en la base de datos

Procesar por lotes, con manejo de error por archivo

Borrar los archivos temporales

Bloquear los procesamientos simultáneos

Crear la pantalla con el botón y el resumen Implementar el bloqueo contra procesamientos simultáneos

Crear la vista con la acción de procesamiento y el resumen
