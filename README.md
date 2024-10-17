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
![image](https://github.com/user-attachments/assets/db9539c3-5511-4bf9-a3c7-0e33245fe058)

**Situación 9**:
El plano se mantendrá en su lugar debido a su Rigidbody sin gravedad. El cubo caerá por gravedad y podrá interactuar físicamente con otros objetos. La esfera caerá debido a la gravedad (porque tiene un Rigidbody), pero no interactuará físicamente con otros objetos, ya que es un Trigger. En cambio, podrá detectar otros objetos que la atraviesen.

![Situación 9](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/practica3-SampleScene-Windows_-Mac_-Linux-Unity-2021.3.38f1-Education_-_DX11_-2024-10-13-23-00-00.gif)


### Siguiente Ejercicio:
**Ejercicio 1**
![video 1](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/My-project3_b_-SampleScene-Windows_-Mac_-Linux-Unity-2021.3%20(1).gif)

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class movimientocubo : MonoBehaviour
{
    // Campo para la velocidad que será modificable desde el inspector
    public float velocidad = 5f;

    // Update se llama una vez por frame
    void Update()
    {
        // Obtener los valores del input del eje horizontal y vertical
        float ejeHorizontal = Input.GetAxis("Horizontal");
        float ejeVertical = Input.GetAxis("Vertical");

        // Comprobar si se presionan las teclas de las flechas
        if (Input.GetKey(KeyCode.UpArrow))
        {
            Debug.Log("Flecha Arriba: " + (velocidad * ejeVertical));
        }
        if (Input.GetKey(KeyCode.DownArrow))
        {
            Debug.Log("Flecha Abajo: " + (velocidad * ejeVertical));
        }
        if (Input.GetKey(KeyCode.LeftArrow))
        {
            Debug.Log("Flecha Izquierda: " + (velocidad * ejeHorizontal));
        }
        if (Input.GetKey(KeyCode.RightArrow))
        {
            Debug.Log("Flecha Derecha: " + (velocidad * ejeHorizontal));
        }
    }
}
```
**Ejercicio 2**

![image](https://github.com/user-attachments/assets/25293050-7cc2-4225-a6a7-6f061c62fcc5)
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class disparo : MonoBehaviour
{
    // Método que simula el disparo
    void Disparar()
    {
        // Esto es solo un ejemplo de lo que puede ocurrir al disparar.
        // Podrías instanciar un proyectil o mostrar una animación.
        Debug.Log("¡Disparo ejecutado!");
    }

    // Update se llama una vez por frame
    void Update()
    {
        // Revisar si la tecla asignada para "Disparo" (en nuestro caso la tecla H) es presionada
        if (Input.GetButtonDown("Disparo"))
        {
            Disparar();
        }
    }
}


**Ejercicio 3**
duplicas las coordenadas de la dirección del movimiento: El cubo debería moverse más rápido en esa dirección, ya que el vector de dirección ahora es el doble de grande.
duplicas la velocidad manteniendo la dirección del movimiento: El cubo se moverá al doble de la velocidad.
la velocidad que usas es menor que 1:El cubo se moverá más lentamente.
la posición del cubo tiene y>0: El cubo se desplazará en el eje X (o en la dirección definida en moveDirection), pero su altura en el eje y permanecerá constante. El movimiento no afectará la posición y a menos que la cambies en moveDirection.
intercambiar movimiento relativo al sistema de referencia local y el mundial: Con Space.World: El cubo se moverá de acuerdo al sistema de coordenadas globales, sin importar su rotación.
Con Space.Self: El cubo se moverá en función de su orientación actual. Por ejemplo, si el cubo está rotado, se moverá en su "propia" dirección frontal, no necesariamente alineado con los ejes globales.


using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class movimientoCuboAvanzado : MonoBehaviour
{
    // Velocidad de movimiento, se puede modificar desde el Inspector.
    public float speed = 2f;  // Debe ser mayor que 1 como se indica.
    
    // Dirección del movimiento, se puede modificar desde el Inspector.
    public Vector3 moveDirection = new Vector3(1f, 0f, 0f);  // Movimiento inicial hacia el eje X.

    // Update se llama una vez por frame.
    void Update()
    {
        // Trasladar el cubo multiplicando la dirección por la velocidad y por el tiempo.
        // Se puede utilizar el sistema de referencia local o global.
        transform.Translate(moveDirection * speed * Time.deltaTime, Space.World);
    }
}

**Ejercicio 4**
![video 4](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/My-project3_b_-SampleScene-Windows_-Mac_-Linux-Unity-2021.3%20(2).gif)
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class movimientocubo : MonoBehaviour
{
    // Campo para la velocidad que será modificable desde el inspector
    public float velocidad = 5f;

    // Update se llama una vez por frame
    void Update()
    {
        // Obtener los valores del input del eje horizontal y vertical
        float ejeHorizontal = Input.GetAxis("Horizontal");
        float ejeVertical = Input.GetAxis("Vertical");

        // Comprobar si se presionan las teclas de las flechas
        if (Input.GetKey(KeyCode.UpArrow))
        {
            Debug.Log("Flecha Arriba: " + (velocidad * ejeVertical));
        }
        if (Input.GetKey(KeyCode.DownArrow))
        {
            Debug.Log("Flecha Abajo: " + (velocidad * ejeVertical));
        }
        if (Input.GetKey(KeyCode.LeftArrow))
        {
            Debug.Log("Flecha Izquierda: " + (velocidad * ejeHorizontal));
        }
        if (Input.GetKey(KeyCode.RightArrow))
        {
            Debug.Log("Flecha Derecha: " + (velocidad * ejeHorizontal));
        }
    }
}

**Ejercicio 5**
En este ejercicio no pongo video ya que el resultado es el mismo que en el anterior. El Time.DeltaTime sirve en el caso de que si el juego corre en un ordenador con una tasa de frames baja o alta, el movimiento de los objetos seguirá siendo consistente.

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class objetosmovimiento : MonoBehaviour
{
    // Velocidades para el cubo y la esfera (modificables desde el Inspector)
    public float speedCubo = 5f;
    public float speedEsfera = 5f;

    // Referencias al cubo y a la esfera (asignables desde el Inspector)
    public GameObject cubo;
    public GameObject esfera;

    void Update()
    {
        // Movimiento del cubo con las teclas de flecha
        MoverCubo();

        // Movimiento de la esfera con las teclas WASD
        MoverEsfera();
    }

    // Función para mover el cubo con las flechas
    void MoverCubo()
    {
        // // Obtener el input del eje horizontal y vertical solo para el cubo (flechas)
        // float moveHorizontalCubo = Input.GetAxisRaw("Horizontal"); // Flechas izquierda/derecha
        // float moveVerticalCubo = Input.GetAxisRaw("Vertical");     // Flechas arriba/abajo
        float moveHorizontalCubo = 0f;
        float moveVerticalCubo = 0f;
        if (Input.GetKey(KeyCode.UpArrow)) { moveVerticalCubo = 1f; }    // W: mover hacia adelante
        if (Input.GetKey(KeyCode.DownArrow)) { moveVerticalCubo = -1f; }   // S: mover hacia atrás
        if (Input.GetKey(KeyCode.LeftArrow)) { moveHorizontalCubo = -1f; } // A: mover hacia izquierda
        if (Input.GetKey(KeyCode.RightArrow)) { moveHorizontalCubo = 1f; }  // D: mover hacia derecha
        // Crear el vector de movimiento para el cubo
        Vector3 moveDirectionCubo = new Vector3(moveHorizontalCubo, 0f, moveVerticalCubo);

        // Aplicar el movimiento al cubo
        cubo.transform.Translate(moveDirectionCubo * speedCubo * Time.deltaTime, Space.World);
    }

    // Función para mover la esfera con las teclas WASD exclusivamente con Input.GetKey
    void MoverEsfera()
    {
        // Input directo para movimiento WASD de la esfera
        float moveHorizontalEsfera = 0f;
        float moveVerticalEsfera = 0f;

        // Detectar las teclas WASD exclusivamente para la esfera
        if (Input.GetKey(KeyCode.W)) { moveVerticalEsfera = 1f; }    // W: mover hacia adelante
        if (Input.GetKey(KeyCode.S)) { moveVerticalEsfera = -1f; }   // S: mover hacia atrás
        if (Input.GetKey(KeyCode.A)) { moveHorizontalEsfera = -1f; } // A: mover hacia izquierda
        if (Input.GetKey(KeyCode.D)) { moveHorizontalEsfera = 1f; }  // D: mover hacia derecha

        // Crear el vector de movimiento para la esfera
        Vector3 moveDirectionEsfera = new Vector3(moveHorizontalEsfera, 0f, moveVerticalEsfera);

        // Aplicar el movimiento a la esfera
        esfera.transform.Translate(moveDirectionEsfera * speedEsfera * Time.deltaTime, Space.World);
    }
}


**Ejercicio 6**
![video 4](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/My-project3_b_-SampleScene-Windows_-Mac_-Linux-Unity-2021.3%20(3).gif)
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ejer6 : MonoBehaviour
{
    public float speedCubo = 5f;
    public float speedEsfera = 5f;

    public GameObject cubo;
    public GameObject esfera;

    private Vector3 esferaPosicionAnterior;

    void Start()
    {
        esferaPosicionAnterior = esfera.transform.position;
    }

    void Update()
    {
        MoverEsfera();
        SeguirEsfera();
    }

    void MoverEsfera()
    {
        float moveHorizontalEsfera = 0f;
        float moveVerticalEsfera = 0f;

        if (Input.GetKey(KeyCode.W)) { moveVerticalEsfera = 1f; }
        if (Input.GetKey(KeyCode.S)) { moveVerticalEsfera = -1f; }
        if (Input.GetKey(KeyCode.A)) { moveHorizontalEsfera = -1f; }
        if (Input.GetKey(KeyCode.D)) { moveHorizontalEsfera = 1f; }

        Vector3 moveDirectionEsfera = new Vector3(moveHorizontalEsfera, 0f, moveVerticalEsfera);
        esfera.transform.Translate(moveDirectionEsfera * speedEsfera * Time.deltaTime, Space.World);
    }

    void SeguirEsfera()
    {
        Vector3 desplazamientoEsfera = esfera.transform.position - esferaPosicionAnterior;

        // Ignorar cualquier cambio en el eje Y (altura)
        desplazamientoEsfera.y = 0f;

        // Mover el cubo por el mismo desplazamiento, pero sin modificar su altura
        cubo.transform.Translate(desplazamientoEsfera, Space.World);

        esferaPosicionAnterior = esfera.transform.position;
    }
}

**Ejercicio 7**
![video 4](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/My-project3_b_-SampleScene-Windows_-Mac_-Linux-Unity-2021.3_1.gif)

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ejer7 : MonoBehaviour
{
    public float speedEsfera = 5f; // Velocidad de la esfera
    public GameObject cubo;        // Referencia al cubo
    public GameObject esfera;      // Referencia a la esfera

    private float distanciaInicial; // Distancia inicial entre el cubo y la esfera

    void Start()
    {
        // Calcular la distancia inicial entre el cubo y la esfera, ignorando la altura (eje Y)
        Vector3 diferenciaInicial = esfera.transform.position - cubo.transform.position;
        diferenciaInicial.y = 0f; // Ignoramos la altura
        distanciaInicial = diferenciaInicial.magnitude;
    }

    void Update()
    {
        // Mover la esfera con las teclas WASD
        MoverEsfera();

        // Hacer que el cubo siga y gire hacia la esfera, manteniendo la distancia inicial
        SeguirEsferaManteniendoDistancia();
    }

    void MoverEsfera()
    {
        float moveHorizontalEsfera = 0f;
        float moveVerticalEsfera = 0f;

        // Detectar teclas WASD para mover la esfera
        if (Input.GetKey(KeyCode.W)) { moveVerticalEsfera = 1f; }
        if (Input.GetKey(KeyCode.S)) { moveVerticalEsfera = -1f; }
        if (Input.GetKey(KeyCode.A)) { moveHorizontalEsfera = -1f; }
        if (Input.GetKey(KeyCode.D)) { moveHorizontalEsfera = 1f; }

        Vector3 moveDirectionEsfera = new Vector3(moveHorizontalEsfera, 0f, moveVerticalEsfera);
        esfera.transform.Translate(moveDirectionEsfera * speedEsfera * Time.deltaTime, Space.World);
    }

    void SeguirEsferaManteniendoDistancia()
    {
        // Obtener la dirección hacia la esfera
        Vector3 direccionHaciaEsfera = esfera.transform.position - cubo.transform.position;

        // Mantener la altura constante (ignorar cambios en el eje Y)
        direccionHaciaEsfera.y = 0f;

        // Normalizar el vector dirección para que el cubo siga en la misma dirección sin cambiar la magnitud
        Vector3 direccionNormalizada = direccionHaciaEsfera.normalized;

        // Calcular la nueva posición del cubo manteniendo la distancia inicial
        Vector3 nuevaPosicion = esfera.transform.position - direccionNormalizada * distanciaInicial;

        // Rotar el cubo para que apunte hacia la esfera
        cubo.transform.LookAt(new Vector3(esfera.transform.position.x, cubo.transform.position.y, esfera.transform.position.z));

        // Mover el cubo a la nueva posición, manteniendo la distancia inicial
        cubo.transform.position = Vector3.Lerp(cubo.transform.position, nuevaPosicion, Time.deltaTime * 5f);
    }
}

**Ejercicio 8**
![video 4](https://github.com/SergioPerezLoza/p3_interfaces_inteligentes/blob/main/My-project3_b_-SampleScene-Windows_-Mac_-Linux-Unity-2021.3_1%20(1).gif)

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ejer8 : MonoBehaviour
{
    public float velocidadMovimiento = 5f; // Velocidad de movimiento hacia adelante
    public float velocidadRotacion = 100f; // Velocidad de rotación (giro con las flechas izquierda/derecha)

    void Update()
    {
        // Obtener input horizontal (teclas A/D o flechas izquierda/derecha)
        float inputHorizontal = Input.GetAxis("Horizontal");

        // Girar el objeto en el eje Y (rotación)
        transform.Rotate(0f, inputHorizontal * velocidadRotacion * Time.deltaTime, 0f);

        // Avanzar siempre en la dirección hacia adelante (forward)
        transform.Translate(transform.forward * velocidadMovimiento * Time.deltaTime, Space.World);

        // Dibujar una línea (ray) para depurar la dirección hacia adelante
        Debug.DrawRay(transform.position, transform.forward * 2f, Color.red);
    }
}

**Ejercicio 9**
![image](https://github.com/user-attachments/assets/d8e89169-f957-4cff-b13b-76e07fd32a6a)
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class DeteccionColision : MonoBehaviour
{
    // Este método se ejecuta cuando el cilindro detecta una colisión con otro objeto
    private void OnCollisionEnter(Collision collision)
    {
        // Obtener el objeto que ha colisionado y su etiqueta
        GameObject objetoColisionado = collision.gameObject;

        // Mostrar en la consola el mensaje con la etiqueta del objeto
        Debug.Log("El objeto con la etiqueta: " + objetoColisionado.tag + " ha colisionado con el cilindro.");
    }
}


**Ejercicio 10**
![image](https://github.com/user-attachments/assets/9d8c59e7-3167-446a-b886-95af7edc5a97)

  using UnityEngine;

public class ejer10 : MonoBehaviour
{
    // Detectar colisiones físicas normales (Esfera)
    private void OnCollisionEnter(Collision collision)
    {
        Debug.Log("Colisión con el objeto: " + collision.gameObject.tag);
    }

    // Detectar triggers (Cubo cinemático con trigger activado)
    private void OnTriggerEnter(Collider other)
    {
        Debug.Log("Trigger activado por: " + other.gameObject.tag);
    }
}

**Ejercicio 11**
![image](https://github.com/user-attachments/assets/6b8106d3-9418-4a14-9266-0c610c426780)

using UnityEngine;

public class ejer11 : MonoBehaviour
{
    // Este método detectará cuando un objeto entre en el trigger del Cilindro
    private void OnTriggerEnter(Collider other)
    {
        // Obtener la etiqueta del objeto que activó el trigger
        string tagObjetoColisionado = other.gameObject.tag;
        Debug.Log("Trigger activado por: " + tagObjetoColisionado);
    }
}

**Ejercicio 12**


**Esfera con mayor masa que el Cilindro**:
La Esfera tiene una gran influencia en las colisiones. El Cilindro es empujado considerablemente por la Esfera debido a la diferencia de masa.

**Esfera con menor masa que el Cilindro**:
El Cilindro empuja fácilmente la Esfera. El impacto en la Esfera es grande, mientras que el Cilindro casi no se ve afectado.

**Esfera como cinemática**:
La Esfera permanece inmóvil al colisionar con el Cilindro, pero este es empujado o detenido según la dirección y fuerza aplicada.

**Esfera como Trigger**:
El Cilindro atraviesa la Esfera sin interacción física, aunque puede dispararse un evento de colisión a través de scripts si se usa OnTriggerEnter.

using UnityEngine;

public class ejer12 : MonoBehaviour
{
    public float velocidad = 10f;  // Velocidad del movimiento
    public float rotacionVelocidad = 100f;  // Velocidad de rotación
    private Rigidbody rb;  // Referencia al componente Rigidbody

    void Start()
    {
        // Obtenemos el componente Rigidbody del Cilindro
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        // Leer las entradas del teclado
        float moverAdelante = 0f;
        float moverLateral = 0f;

        // Nuevas teclas para controlar el movimiento:
        // I - hacia adelante
        // K - hacia atrás
        // J - girar a la izquierda
        // L - girar a la derecha

        if (Input.GetKey(KeyCode.I)) 
        {
            moverAdelante = 1f;  // Mover hacia adelante
        }
        if (Input.GetKey(KeyCode.K)) 
        {
            moverAdelante = -1f;  // Mover hacia atrás
        }
        if (Input.GetKey(KeyCode.J)) 
        {
            moverLateral = -1f;  // Girar hacia la izquierda
        }
        if (Input.GetKey(KeyCode.L)) 
        {
            moverLateral = 1f;  // Girar hacia la derecha
        }

        // Aplicar movimiento hacia adelante o atrás
        Vector3 movimiento = transform.forward * moverAdelante * velocidad * Time.deltaTime;
        rb.MovePosition(rb.position + movimiento);

        // Aplicar rotación
        float rotacion = moverLateral * rotacionVelocidad * Time.deltaTime;
        Quaternion rot = Quaternion.Euler(0f, rotacion, 0f);
        rb.MoveRotation(rb.rotation * rot);
    }
}


**Ajuste de fricción del Cilindro**:
Con fricción alta, el Cilindro se mueve lentamente y se detiene rápidamente.
Con fricción baja, el Cilindro se desliza y tarda más en detenerse después de recibir una fuerza o impulso.
