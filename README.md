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
