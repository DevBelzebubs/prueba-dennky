# Prueba técnica

Interfaz de registro inspirada en la referencia visual. El proyecto está construido con Vue 3, TypeScript, Vite y Tailwind CSS 4.

## Requisitos

- Node.js `^22.18.0` o `>=24.12.0`, según lo declarado en `package.json`.
- npm.

## Cómo levantar el proyecto

Desde la carpeta `prueba-tecnica`, ejecuta:

```sh
npm install
npm run dev
```

Abre en el navegador la dirección local que muestre Vite en la terminal (normalmente `http://localhost:5173`).

Para comprobar los tipos y generar la versión de producción:

```sh
npm run build
```

Este comando ejecuta el chequeo de tipos con `vue-tsc` y compila la aplicación. Para servir localmente la compilación:

```sh
npm run preview
```

## Qué incluye

- Una página de registro con una composición adaptable a escritorio y móvil.
- Un panel testimonial con imagen local, identidad visual y cita.
- Un formulario con nombre, correo, contraseña y confirmación de contraseña.
- Validación reactiva de campos requeridos, formato del correo, longitud mínima de contraseña y coincidencia entre contraseñas. Los errores aparecen al salir del campo o al enviar y se actualizan al corregir los valores.
- Un modal independiente que avisa cuando se intenta enviar el formulario con campos vacíos. Se puede cerrar con el botón, con Escape o haciendo clic fuera del diálogo.
- Estilos construidos con clases utilitarias de Tailwind CSS.

La interfaz es únicamente de presentación: el formulario no crea cuentas ni se conecta a una API. El botón de Google tampoco inicia un flujo de autenticación.

## Pasos realizados

1. Revisé la estructura inicial del proyecto Vue y mantuve Vite y TypeScript como base.
2. Organicé la pantalla en una vista principal y componentes separados para el formulario y el panel testimonial.
3. Configuré Tailwind CSS 4 mediante su plugin para Vite y reemplacé los estilos específicos de los componentes por clases utilitarias.
4. Añadí la ruta de inicio y ajusté la composición para que se adapte a pantallas pequeñas.
5. Amplié el formulario con validación reactiva y extraje el aviso de campos vacíos a un componente de modal independiente.
6. Ejecuté `npm run build` para comprobar el chequeo de tipos y la compilación de producción.

## Lo que aprendí

- Vue permite derivar los errores de validación del estado reactivo del formulario, evitando mantener mensajes y valores sincronizados manualmente.
- Separar el modal y los paneles visuales en componentes hace que la vista sea más fácil de entender y mantener.
- Tailwind CSS 4 se integra con Vite mediante su plugin y permite mantener los estilos junto a la estructura del componente.
- En plantillas Vue, el orden y el cierre correcto de las etiquetas son importantes: un elemento mal anidado puede detener el análisis de la plantilla antes de que la aplicación arranque.

## Retos y mejoras posibles

Lo que más costó fue ajustar la composición visual para distintos tamaños y combinar la validación de varios campos con una respuesta clara al enviar el formulario. También fue necesario prestar atención a la sintaxis de la plantilla Vue, ya que un error de etiquetas puede manifestarse como un error de compilación de Vite.

Como siguientes pasos, se podría:

- Conectar el formulario con una API y añadir estados de carga, éxito y error.
- Implementar autenticación real, incluida la integración con Google si el producto la requiere.
- Incorporar una estrategia de fallback o servir localmente las fuentes para reducir dependencias de recursos externos.