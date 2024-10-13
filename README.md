# p3_interfaces_inteligentes

## alu0101473260@ull.edu.es
## Sergio Pérez Lozano

### Ejercicios Física 3D
**Situación 1**:
Al iniciar el juego, el cubo (que tiene un Rigidbody) caerá sobre el plano debido a la gravedad. Como el plano tiene un Collider, el cubo no atravesará el plano y se quedará encima.
La esfera no será afectada por la gravedad porque no tiene un Rigidbody, y tampoco se moverá. Sin embargo, el Box Collider del cubo detectará colisiones si entra en contacto con la esfera, pero la esfera se quedará inmóvil porque no es un objeto físico.
![image](https://github.com/user-attachments/assets/f5b21604-f3ee-4c54-847a-c1676864686a)

**Situación 2**:
Al iniciar el juego, tanto el cubo como la esfera caerán hacia el plano debido a la gravedad, ya que ambos tienen Rigidbody y la opción Use Gravity está activada.
Ambos objetos colisionarán con el plano debido a los colliders del plano, del cubo y de la esfera.
El cubo y la esfera también colisionarán entre sí si entran en contacto, ya que ambos tienen Rigidbody y colliders.
![Video 2](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/practica3-SampleScene-Windows_-Mac_-Linux-Unity-2021.3.38f1-Education_-_DX11_-2024-10-13-15-40-29.gif)

**Situación 3**:
Al iniciar el juego, el cubo caerá hacia el plano debido a la gravedad y aterrizará sobre el plano, ya que ambos tienen colliders.
La esfera, al estar en modo cinemático, no caerá ni se moverá debido a la gravedad. En su lugar, permanecerá en su posición actual hasta que sea movida explícitamente a través de un script o manipulación manual.
El cubo y la esfera podrán colisionar entre sí, pero la esfera no será afectada por la colisión debido a que es cinemática. Sin embargo, la esfera sí puede empujar al cubo si es movida a través de un script.
![image](https://github.com/user-attachments/assets/693d20fc-5a86-4f49-910f-67039ec1a5f9)

**Situación 4**:
Al iniciar el juego, tanto el cubo como la esfera serán afectados por la gravedad y caerán sobre el plano.
El plano no se moverá debido a que está marcado como cinemático, pero actuará como una superficie sólida donde los otros objetos (cubo y esfera) podrán caer y reposar.
La esfera y el cubo colisionarán entre sí y con el plano. Ambos responderán a las fuerzas físicas, como el rebote o el deslizamiento sobre el plano, dependiendo de sus propiedades físicas.
![Video 2](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/practica3-SampleScene-Windows_-Mac_-Linux-Unity-2021.3.38f1-Education_-_DX11_-2024-10-13-15-40-29.gif)

**Situación 5**:
Todos los objetos caerán al mismo tiempo debido a la gravedad, pero la esfera tendrá una mayor inercia y podría rebotar de manera diferente al cubo debido a la diferencia de masas.
Al colisionar, el cubo será más afectado que la esfera, es decir, se moverá más.
Cuando los objetos interactúan entre sí, el cubo tiende a moverse más rápido que la esfera en colisiones directas debido a su menor masa. Esto también puede hacer que el cubo "salte" o se desplace más rápidamente que la esfera.

![situacion 5](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/practica3-SampleScene-Windows_-Mac_-Linux-Unity-2021.3.38f1-Education_-_DX11_-2024-10-13-17-07-08.gif)

**Situación 6**:
En este caso con la esfera 100 con veces más masa que el cubo en lugar de 10, el comportamiento esperado será similar, pero con un mayor impacto en la física, especialmente en situaciones de colisiones como se puede observar cuando impacta con el cubo

![situacion 6](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/practica3-SampleScene-Windows_-Mac_-Linux-Unity-2021.3.38f1-Education_-_DX11_-2024-10-13-17-16-22.gif)

**Situación 7**:
En esta situación, tanto el cubo como la esfera caerán debido a la gravedad. El cubo se deslizará sobre el plano al caer, mientras que la esfera, debido a su fricción, se detendrá más rápidamente al hacer contacto con el plano, resistiendo más el movimiento. La fricción de la esfera hará que se adhiera mejor a la superficie.
![situacion 7](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/practica3-SampleScene-Windows_-Mac_-Linux-Unity-2021.3.38f1-Education_-_DX11_-2024-10-13-22-48-37.gif)
**Situación 8**:
El plano permanecerá en su lugar porque tiene un Rigidbody pero sin gravedad.El cubo caerá debido a la gravedad. La esfera no caerá ni interactuará físicamente con los otros objetos, pero podrá detectar colisiones debido a su Trigger.
![imagen 8](![image](https://github.com/user-attachments/assets/db9539c3-5511-4bf9-a3c7-0e33245fe058)

**Situación 9**:
El plano se mantendrá en su lugar debido a su Rigidbody sin gravedad. El cubo caerá por gravedad y podrá interactuar físicamente con otros objetos. La esfera caerá debido a la gravedad (porque tiene un Rigidbody), pero no interactuará físicamente con otros objetos, ya que es un Trigger. En cambio, podrá detectar otros objetos que la atraviesen.

![Situación 9](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/practica3-SampleScene-Windows_-Mac_-Linux-Unity-2021.3.38f1-Education_-_DX11_-2024-10-13-23-00-00.gif)
