# 15 Puzzle Game - SvelteKit

Este es un clásico juego de rompecabezas conocido como el **15 Puzzle**, implementado utilizando **SvelteKit**. El objetivo del juego es ordenar los números del 1 al 15 en orden ascendente, dejando el espacio vacío en la esquina inferior derecha.

## Características

- **Interfaz intuitiva**: Diseño limpio y fácil de usar.
- **Movimientos fluidos**: Los bloques se deslizan suavemente al hacer clic.
- **Reinicio del juego**: Puedes reiniciar el juego en cualquier momento para comenzar de nuevo.
- **Contador de movimientos**: Lleva un registro de cuántos movimientos has realizado.
- **Responsivo**: Funciona en dispositivos móviles y de escritorio.

## Instalación

Para ejecutar este proyecto localmente, sigue estos pasos:

1. **Clona el repositorio**:
   ```bash
   git clone https://github.com/ingfranciscastillo/fifteen-puzzle.git
   cd 
   ```
2. **Instala las dependencias:**:
   ```bash
    bun install
   ```
3. **Inicia el servidor de desarrollo:**:
   ```bash
    bun run dev --open
   ```
3. **Abre el proyecto en tu navegador:**:

Visita http://localhost:5173 para ver el juego en acción.

## Cómo jugar

    Haz clic en cualquier número adyacente al espacio vacío para moverlo.

    El objetivo es ordenar los números del 1 al 15 en orden ascendente.

    El espacio vacío debe quedar en la esquina inferior derecha.

## Estructura del Proyecto

    src/routes/+page.svelte: Contiene la lógica principal del juego y la interfaz de usuario.

    src/lib/: Aquí puedes encontrar componentes reutilizables y utilidades.

    static/: Contiene los archivos estáticos como imágenes o estilos globales.

## Personalización

Si deseas personalizar el juego, puedes modificar los estilos en src/app.css o agregar nuevas funcionalidades en src/routes/+page.svelte.

## Licencia

Este proyecto está bajo la licencia MIT. Siéntete libre de usarlo y modificarlo según tus necesidades.

¡Diviértete jugando y resolviendo el 15 Puzzle! 🎮