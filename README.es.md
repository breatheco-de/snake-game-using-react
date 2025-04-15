<!-- hide -->
# ¡Crea tu Propio Juego de Snake en React!
<!-- endhide -->

<how-to-start>
## 🌱 ¿Cómo iniciar este proyecto?

No clones este repositorio porque vamos a utilizar una plantilla diferente.

Recomendamos abrir la `plantilla de React` utilizando una herramienta de aprovisionamiento como [Codespaces](https://4geeks.com/lesson/what-is-github-codespaces) (recomendado) o [Gitpod](https://4geeks.com/lesson/how-to-use-gitpod). Alternativamente, puedes [clonar el repositorio de GitHub](https://4geeks.com/how-to/github-clone-repository) en tu computadora local usando el comando `git clone`.

Este es el repositorio que necesitas abrir o clonar:

```
https://github.com/4GeeksAcademy/react-hello
```

> ⚠ ¡Necesitarás tener Node.js instalado si lo haces localmente, pero todo eso ya está instalado en Codespaces o Gitpod!

</how-to-start>

## 📝 Instrucciones

### Paso 1: Configura el Proyecto

- [ ] Configura el proyecto boilerplate desde la plantilla de React proporcionada.
  
- [ ] Sigue las instrucciones en el README del repositorio para configurar tu entorno de desarrollo.

### Paso 2: Planifica la Estructura del Juego

- [ ] Crea un boceto o diagrama de cómo será tu juego de Snake.

  - ¿Cómo representarás el tablero de juego?
  - ¿Cómo manejarás el estado de la serpiente y la comida?
  - ¿Qué componentes necesitarás?

### Paso 3: Implementa el Tablero de Juego

- [ ] Crea un componente `Board` que representará el área donde se moverá la serpiente.

- [ ] Define el tamaño del tablero (por ejemplo, una cuadrícula de 20x20).

- [ ] Usa CSS para estilizar el tablero y las celdas.

### Paso 4: Maneja el Estado con useState

- [ ] Utiliza el hook `useState` para manejar:

  - La posición de la serpiente (un array de coordenadas).
  - La dirección actual de movimiento.
  - La posición de la comida.
  - El estado del juego (en curso, finalizado).

```jsx
const [snake, setSnake] = useState([[10, 10]]);
const [direction, setDirection] = useState('RIGHT');
const [food, setFood] = useState([15, 15]);
const [gameOver, setGameOver] = useState(false);
```

### Paso 5: Maneja el Movimiento de la Serpiente

- [ ] Usa el hook `useEffect` para crear un bucle de juego que actualice la posición de la serpiente en intervalos regulares.

- [ ] Calcula la nueva cabeza de la serpiente basándote en la dirección actual.

- [ ] Verifica las colisiones con las paredes o con la propia serpiente.

```jsx
useEffect(() => {
  const moveSnake = () => {
    // Lógica para mover la serpiente
  };

  if (!gameOver) {
    const interval = setInterval(moveSnake, 200);
    return () => clearInterval(interval);
  }
}, [snake, direction, gameOver]);
```

### Paso 6: Control de Teclas para Cambiar de Dirección

- [ ] Agrega un event listener para las teclas de flecha y actualiza la dirección de la serpiente en consecuencia.

```jsx
useEffect(() => {
  const handleKeyDown = (event) => {
    switch(event.key) {
      case 'ArrowUp':
        setDirection('UP');
        break;
      case 'ArrowDown':
        setDirection('DOWN');
        break;
      case 'ArrowLeft':
        setDirection('LEFT');
        break;
      case 'ArrowRight':
        setDirection('RIGHT');
        break;
      default:
        break;
    }
  };

  window.addEventListener('keydown', handleKeyDown);
  return () => window.removeEventListener('keydown', handleKeyDown);
}, []);
```

### Paso 7: Implementa la Lógica de la Comida

- [ ] Cuando la serpiente coma la comida:

  - Incrementa la longitud de la serpiente.
  - Genera una nueva posición aleatoria para la comida.

- [ ] Asegúrate de que la comida no aparezca en una posición ocupada por la serpiente.

### Paso 8: Maneja el Fin del Juego

- [ ] Determina cuándo el juego ha terminado (colisión con paredes o consigo misma).

- [ ] Muestra un mensaje de "¡Juego Terminado!" y ofrece la opción de reiniciar el juego.

```jsx
if (checkCollision(newHead)) {
  setGameOver(true);
}
```

### Paso 9: Mejora la Interfaz de Usuario

- [ ] Agrega elementos visuales como:

  - Puntuación actual (basada en la longitud de la serpiente o cantidad de comida consumida).
  - Botón para reiniciar el juego.
  - Indicadores visuales para la comida y la serpiente.

- [ ] Asegúrate de que el juego sea responsivo y se vea bien en diferentes dispositivos.

## Sección de Bonus

### Características Adicionales para Practicar y Mejorar el Proyecto

1. **Ajuste de Velocidad:** Incrementa la velocidad de la serpiente a medida que el jugador avanza.

2. **Niveles de Dificultad:** Ofrece diferentes niveles de dificultad con velocidades o tamaños de tablero variados.

3. **Obstáculos:** Agrega obstáculos al tablero que la serpiente debe evitar.

4. **Sonidos y Efectos:** ¡Añade efectos de sonido al comer la comida o al finalizar el juego!

5. **Puntuaciones Altas:** Implementa un sistema para guardar y mostrar las puntuaciones más altas usando el almacenamiento local.

6. **Temas Personalizables:** Permite al jugador elegir entre diferentes temas visuales para el juego.

7. **Juego Multijugador:** Implementa un modo de juego donde dos serpientes compiten en el mismo tablero.

¡Explora diferentes mejoras para hacer tu juego de Snake más interesante y desafiante!
