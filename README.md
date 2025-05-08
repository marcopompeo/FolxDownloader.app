Solo para Mac.
Es una app que he creado con Apple Script para poder descargar masivamente con la app Folx desde un txt con muchas urls.


AppleScript para FOLX:
Abre Script Editor (⌘ + Espacio y escribe “Editor de secuencias de comandos”).

Pega esto:

applescript
Copiar
Editar
set filePath to (choose file with prompt "Selecciona tu archivo .txt con URLs:" of type {"txt"}) as text
set fileRef to open for access file filePath
set urlList to paragraphs of (read fileRef)
close access fileRef

repeat with theURL in urlList
	if theURL is not "" then
		do shell script "open -a Folx \"" & theURL & "\""
	end if
end repeat
Luego ve a Archivo > Guardar:

Nombre: lo que tú quieras (ej. Descargas Folx)

Formato de archivo: selecciona "Aplicación"

Marca la casilla "Mantener abierto después de ejecutar" desactivada

Ahora solo tienes que hacer doble clic en esa "app", elegir tu archivo .txt con URLs, y ¡FOLX abrirá todas las descargas automáticamente!
