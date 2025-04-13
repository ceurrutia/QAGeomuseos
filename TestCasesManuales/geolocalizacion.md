# Caso de prueba manual: Geolocalización en la página de inicio

## Nombre del test:

Verificar que la página index solicita y maneja correctamente la geolocalización del usuario.

## Objetivo: Comprobar que al cargar la página principal:

1. Se solicita permiso de geolocalización.
2. Se obtiene la ubicación si se acepta.
3. Se maneja el rechazo de permiso si el usuario lo niega.

## Precondiciones:

Navegador moderno con soporte para geolocalización (Chrome, Firefox, etc.).
Acceso a la URL / (home de Geomuseos).
Javascript habilitado.
No tener un bloqueo automático de geolocalización para el sitio.

## Pasos para ejecutar el test:

### Paso 1: Acción	Resultado Esperado

1. Abrir el navegador y acceder a http://localhost:8000/ si esta en local o https://geomuseos.onrender.com y se carga la página index.html correctamente.
2. Observar si el navegador solicita permiso de ubicación: Aparece un popup arriba a la izquierda preguntando: "¿Quieres compartir tu ubicación con este sitio?" 
3. Aceptar el permiso de ubicación: La página debe mostrar un marcador o mostrar ua alerta verde en el primer scroll con la ubicación del usuario.
4. Recargar la página y negar el permiso de ubicación: El sistema debe mostrar un mensaje de error, alerta o un fallback (por ejemplo: "Ubicación no disponible")
5. Revisar la consola del navegador (F12 > Consola)	No debe haber errores JS, y se deben mostrar logs como Ubicación obtenida o Error al obtener ubicación.

## Criterios de aceptación

* El sitio solicita correctamente permiso de geolocalización.
* Al aceptar, obtiene la ubicación (Nombre de la ciudad).
* Al rechazar, solo muestra museos en ciudades random.
* No hay errores en consola relacionados con navigator.geolocation.