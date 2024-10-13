# p3_interfaces_inteligentes

## alu0101473260@ull.edu.es
## Sergio Pérez Lozano

### Ejercicios Física 3D
Situación 1:
Al iniciar el juego, el cubo (que tiene un Rigidbody) caerá sobre el plano debido a la gravedad. Como el plano tiene un Collider, el cubo no atravesará el plano y se quedará encima.
La esfera no será afectada por la gravedad porque no tiene un Rigidbody, y tampoco se moverá. Sin embargo, el Box Collider del cubo detectará colisiones si entra en contacto con la esfera, pero la esfera se quedará inmóvil porque no es un objeto físico.
