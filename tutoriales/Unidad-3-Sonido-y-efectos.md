# UNIDAD 3: SONIDOS Y EFECTOS 

##  INFORMACIÓN GENERAL
- **Ubicación:** `tutoriales/unidad-3-Sonidos-y-efectos.md`
- **Objetivo:** Implementar sistema de salto y generación de obstáculos

# UNIDAD 3: SONIDOS Y EFECTOS - ÍNDICE

## 📑 ÍNDICE DE NAVEGACIÓN

### [INFORMACIÓN GENERAL](#información-general)

### [LECCIÓN 3.1: FUERZA DE SALTO](#lección-31-fuerza-de-salto)
- [1. ¿Cómo abrir el prototipo y cambiar el fondo?](#1-cómo-abrir-el-prototipo-y-cambiar-el-fondo)
- [2. ¿Cómo elegir y configurar un personaje jugador?](#2-cómo-elegir-y-configurar-un-personaje-jugador)
- [3. ¿Cómo hacer que el jugador salte al inicio?](#3-cómo-hacer-que-el-jugador-salte-al-inicio)
- [4. ¿Cómo hacer que el jugador salte si se presiona la barra espaciadora?](#4-cómo-hacer-que-el-jugador-salte-si-se-presiona-la-barra-espaciadora)
- [5. ¿Cómo corregir la fuerza y la gravedad del salto?](#5-cómo-corregir-la-fuerza-y-la-gravedad-del-salto)
- [6. ¿Cómo evitar que el jugador realice saltos dobles?](#6-cómo-evitar-que-el-jugador-realice-saltos-dobles)
- [7. ¿Cómo crear un obstáculo y moverlo a la izquierda?](#7-cómo-crear-un-obstáculo-y-moverlo-a-la-izquierda)
- [8. ¿Cómo crear un Spawn Manager?](#8-cómo-crear-un-spawn-manager)
- [9. ¿Cómo generar obstáculos a intervalos?](#9-cómo-generar-obstáculos-a-intervalos)

### [LECCIÓN 3.2: HAZ QUE EL MUNDO PASE VOLANDO](#lección-32-haz-que-el-mundo-pase-volando)
- [1. ¿Cómo crear un script para repetir el fondo?](#1-cómo-crear-un-script-para-repetir-el-fondo)
- [2. ¿Cómo restablecer la posición del Background?](#2-cómo-restablecer-la-posición-del-background)
- [3. ¿Cómo corregir la repetición del fondo con colisionador?](#3-cómo-corregir-la-repetición-del-fondo-con-colisionador)
- [4. ¿Cómo agregar un nuevo desencadenador de fin del juego?](#4-cómo-agregar-un-nuevo-desencadenador-de-fin-del-juego)
- [5. ¿Cómo detener MoveLeft cuando ocurre un gameOver?](#5-cómo-detener-moveleft-cuando-ocurre-un-gameover)
- [6. ¿Cómo detener la generación de obstáculos durante el gameOver?](#6-cómo-detener-la-generación-de-obstáculos-durante-el-gameover)
- [7. ¿Cómo destruir los obstáculos que sobrepasen los límites?](#7-cómo-destruir-los-obstáculos-que-sobrepasen-los-límites)

### [LECCIÓN 3.3: NO TE QUEDES AHÍ SIN HACER NADA](#lección-33-no-te-quedes-ahí-sin-hacer-nada)
- [1. ¿Cómo explorar las animaciones del jugador?](#1-cómo-explorar-las-animaciones-del-jugador)
- [2. ¿Cómo hacer que el jugador comience corriendo?](#2-cómo-hacer-que-el-jugador-comience-corriendo)
- [3. ¿Cómo configurar una animación de salto?](#3-cómo-configurar-una-animación-de-salto)
- [4. ¿Cómo ajustar la animación de salto?](#4-cómo-ajustar-la-animación-de-salto)
- [5. ¿Cómo configurar una animación de caída?](#5-cómo-configurar-una-animación-de-caída)
- [6. ¿Cómo evitar que el jugador salte mientras está inconsciente?](#6-cómo-evitar-que-el-jugador-salte-mientras-está-inconsciente)

### [LECCIÓN 3.4: EFECTOS DE SONIDO Y PARTÍCULAS](#lección-34-efectos-de-sonido-y-partículas)
- [1. ¿Cómo personalizar una partícula de explosión?](#1-cómo-personalizar-una-partícula-de-explosión)
- [2. ¿Cómo reproducir la partícula al momento de la colisión?](#2-cómo-reproducir-la-partícula-al-momento-de-la-colisión)
- [3. ¿Cómo agregar una partícula de salpicadura de polvo?](#3-cómo-agregar-una-partícula-de-salpicadura-de-polvo)
- [4. ¿Cómo agregar música al objeto de cámara?](#4-cómo-agregar-música-al-objeto-de-cámara)
- [5. ¿Cómo declarar variables para Clips de audio?](#5-cómo-declarar-variables-para-clips-de-audio)
- [6. ¿Cómo reproducir clips de audio al saltar y al chocar?](#6-cómo-reproducir-clips-de-audio-al-saltar-y-al-chocar)

### [VIDEO](#video)


## Lección 3.1: Fuerza de salto

###  SECCIONES DE LA LECCIÓN

#### **1. ¿Cómo abrir el prototipo y cambiar el fondo?**
1. Crear proyecto "Prototype 3" vacío en Unity Hub
2. Descargar e importar "Prototype 3 - Starter Files.unitypackage"
3. Abrir escena Prototype 3 y eliminar escena de muestra
4. Seleccionar objeto Background en Hierarchy
5. En Sprite Renderer > Sprite: seleccionar _City, _Nature o _Town

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/38af1546-9663-43b0-9712-0c54a1bb7e4d" />



#### **2. ¿Cómo elegir y configurar un personaje jugador?**
1. En Course Library > Characters: arrastrar personaje a Hierarchy
2. Renombrar como "Player"
3. Rotar en eje Y para que apunte a la derecha
4. Agregar componente Rigidbody
5. Agregar Box Collider y editar límites
6. Crear carpeta "Scripts" y script "PlayerController"
7. Adjuntar script al jugador
<img width="1919" height="1013" alt="image" src="https://github.com/user-attachments/assets/4ea8fe14-1e27-400d-b16c-80522754bb74" />
   <img width="1919" height="1012" alt="image" src="https://github.com/user-attachments/assets/d61df344-e014-4c72-86d6-47540e9d544c" />


#### **3. ¿Cómo hacer que el jugador salte al inicio?**
1. Declarar `private Rigidbody playerRb;`
2. En Start(): `playerRb = GetComponent<Rigidbody>();`
3. En Start(): usar `AddForce()` para hacer saltar al jugador al inicio

<img width="1916" height="907" alt="image" src="https://github.com/user-attachments/assets/587fe586-216d-4a46-9b4e-f6ef24f7e6ae" />

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/e631778f-18e3-45ef-aef7-2babb3242513" />

#### **4. ¿Cómo hacer que el jugador salte si se presiona la barra espaciadora?**
1. En Update(): condicional `if (Input.GetKeyDown(KeyCode.Space))`
2. Copiar código `AddForce` de Start() al condicional
3. Agregar parámetro `ForceMode.Impulse`
4. Reducir valor multiplicador de fuerza
<img width="1883" height="742" alt="image" src="https://github.com/user-attachments/assets/949cf1b2-1f35-4548-9bc0-e484aee2d62c" />
<img width="1919" height="982" alt="image" src="https://github.com/user-attachments/assets/2980ecd6-417f-4173-aca1-57872feab121" />


#### **5. ¿Cómo corregir la fuerza y la gravedad del salto?**
1. Reemplazar valor hardcodeado con `public float jumpForce`
2. Agregar `public float gravityModifier`
3. En Start(): `Physics.gravity *= gravityModifier;`
4. En Inspector: ajustar mass, gravityModifier y jumpForce
<img width="1919" height="1016" alt="image" src="https://github.com/user-attachments/assets/c14f5c8c-7363-40e8-9396-df76ba7a77ff" />
<img width="1919" height="997" alt="image" src="https://github.com/user-attachments/assets/2ca3caed-d905-4f63-bee2-d630963857b2" />



#### **6. ¿Cómo evitar que el jugador realice saltos dobles?**
1. Agregar `public bool isOnGround = true;`
2. En condicional de salto: `isOnGround = false;`
3. Agregar condición `&& isOnGround` al condicional de salto
4. Crear método `void OnCollisionEnter()` y definir `isOnGround = true;`


<img width="1919" height="1002" alt="image" src="https://github.com/user-attachments/assets/3d4d7032-f94a-45ff-bbdd-03b0581a63cb" />
<img width="1916" height="1015" alt="image" src="https://github.com/user-attachments/assets/6d1614af-241d-4031-80ac-c1aab3729d8e" />

#### **7. ¿Cómo crear un obstáculo y moverlo a la izquierda?**
1. En Course Library > Obstacles: agregar obstáculo
2. Renombrar como "Obstacle" y posicionar
3. Agregar componentes Rigidbody y Box Collider
4. Editar límites del collider
5. Crear carpeta "Prefabs" y crear Original Prefab
6. Crear script "MoveLeft" y aplicarlo al Obstacle
7. En MoveLeft.cs: código para mover a izquierda con variable speed
8. Aplicar MoveLeft al Background
<img width="1919" height="691" alt="image" src="https://github.com/user-attachments/assets/e3880727-689f-48bd-b11d-d58ee5938bc9" />
<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/926586ca-8055-4957-9c11-92dd28738231" />

#### **8. ¿Cómo crear un Spawn Manager?**
1. Crear objeto vacío "Spawn Manager"
2. Aplicar script SpawnManager.cs
3. Declarar `public GameObject obstaclePrefab;`
4. Asignar prefab en Inspector
5. Declarar `private Vector3 spawnPos`
6. En Start(): instanciar prefab de obstáculo
7. Eliminar prefab de la Escena y probar
<img width="1919" height="1023" alt="image" src="https://github.com/user-attachments/assets/470fd77b-a27d-4628-946b-f2fa7f2829dc" />
<img width="1919" height="1005" alt="image" src="https://github.com/user-attachments/assets/995f7c42-3adf-4441-a056-bb7e88ac8b05" />

#### **9. ¿Cómo generar obstáculos a intervalos?**
1. Crear método `void SpawnObstacle()` y mover instanciación allí
2. Crear variables `float startDelay` y `repeatRate`
3. Usar `InvokeRepeating()` para generar en intervalos
4. En Player Rigidbody > Constraints: Freeze todo excepto posición

   <img width="1894" height="783" alt="image" src="https://github.com/user-attachments/assets/ba8c32ee-0fa4-4a30-b828-d774e864da36" />
   <img width="1919" height="999" alt="image" src="https://github.com/user-attachments/assets/82b4785c-be78-4da0-8941-85b61f648692" />

## Lección 3.2: Haz que el mundo pase volando

#### **1. ¿Cómo crear un script para repetir el fondo?**
1. Crear nuevo Script "RepeatBackground.cs"
2. Adjuntar script al objeto Background
<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/053f2ccb-cbd7-4253-9004-9957085d4460" />

#### **2. ¿Cómo restablecer la posición del Background?**
1. Declarar `private Vector3 startPos;`
2. En Start(): `startPos = transform.position;`
3. En Update(): condicional `if` para restablecer posición cuando se mueva cierta distancia
<img width="1904" height="723" alt="image" src="https://github.com/user-attachments/assets/3dc442d4-341d-43d0-b1da-04d8146b9de5" />


#### **3. ¿Cómo corregir la repetición del fondo con colisionador?**
1. Agregar componente Box Collider al Background
2. Declarar `private float repeatWidth;`
3. En Start(): obtener ancho del Box Collider dividido entre 2
4. Incorporar `repeatWidth` en la función de repetición


<img width="1919" height="968" alt="image" src="https://github.com/user-attachments/assets/00b5670f-99e9-41ce-b04c-456a40f6dabb" />

#### **4. ¿Cómo agregar un nuevo desencadenador de fin del juego?**
1. Agregar etiqueta "Ground" al objeto Ground
2. Agregar etiqueta "Obstacle" al Prefab Obstacle
3. En PlayerController: declarar `public bool gameOver;`
4. En OnCollisionEnter(): condicional `if-else` para verificar colisiones
5. Si colisión con "Ground": `isOnGround = true`
6. Si colisión con "Obstacle": `gameOver = true`

   <img width="1919" height="962" alt="image" src="https://github.com/user-attachments/assets/1e0346d4-b2eb-4428-84b3-887b216d4a06" />
<img width="1919" height="1016" alt="image" src="https://github.com/user-attachments/assets/5c123fa3-9da1-48a7-bdaf-9d842c16d1ac" />


#### **5. ¿Cómo detener MoveLeft cuando ocurre un gameOver?**
1. En MoveLeft.cs: declarar `private PlayerController playerControllerScript;`
2. En Start(): inicializar referencia al PlayerController
3. En Update(): envolver `Translate` en condicional que verifique `!gameOver`

   <img width="1919" height="970" alt="image" src="https://github.com/user-attachments/assets/82b0f135-cf55-450a-b862-7041c83b5f06" />


#### **6. ¿Cómo detener la generación de obstáculos durante el gameOver?**
1. En SpawnManager.cs: obtener referencia a `playerControllerScript`
2. Agregar condición para instanciar solo si `gameOver == false`
<img width="1918" height="952" alt="image" src="https://github.com/user-attachments/assets/b4ba2921-a9d3-4910-91c8-cb6eba6593bf" />

#### **7. ¿Cómo destruir los obstáculos que sobrepasen los límites?**
1. En MoveLeft.cs: en Update(), condicional `if` para destruir obstáculos
2. Verificar si posición es menor que `leftBound`
3. Agregar comentarios para mejorar legibilidad del código
<img width="1919" height="982" alt="image" src="https://github.com/user-attachments/assets/8c3cac4a-0711-44d2-8241-6637b9a07981" />

## Lección 3.3: No te quedes ahí sin hacer nada

#### **1. ¿Cómo explorar las animaciones del jugador?**
1. Hacer doble clic en el Animation Controller del jugador
2. Explorar las diferentes Layers disponibles
3. Hacer doble clic en los States para ver sus animaciones
4. Examinar Transitions para entender sus condiciones

<img width="1911" height="1008" alt="image" src="https://github.com/user-attachments/assets/c21d7d58-c40f-434c-88ff-b15e2e747366" />


#### **2. ¿Cómo hacer que el jugador comience corriendo?**
1. En pestaña Parameters: cambiar variable `Speed_f` a 1.0
2. Clic derecho en `Run_Static` → "Set as Layer Default State"
3. Seleccionar estado `Run_Static` y ajustar valor Speed en Inspector
4. Igualar velocidad de animación con velocidad del Background

<img width="1919" height="981" alt="image" src="https://github.com/user-attachments/assets/060446da-825b-42f3-8a2d-b8c7b39b4d33" />

#### **3. ¿Cómo configurar una animación de salto?**
1. En PlayerController.cs: declarar `private Animator playerAnim;`
2. En Start(): `playerAnim = GetComponent<Animator>();`
3. En condicional de salto: `playerAnim.SetTrigger("Jump_trig");`

<img width="1914" height="1011" alt="image" src="https://github.com/user-attachments/assets/8033f60a-ad2f-4246-b974-f45b87260fdc" />

#### **4. ¿Cómo ajustar la animación de salto?**
1. En ventana Animator: seleccionar estado `Running_Jump`
2. En Inspector: reducir valor Speed para disminuir velocidad de animación
3. Ajustar modificadores: Mass, Jump Force y Gravity del jugador
4. Optimizar parámetros para mejor apariencia del salto
<img width="1919" height="1005" alt="image" src="https://github.com/user-attachments/assets/635db972-671d-410e-b9c3-b37dd2e31c57" />

#### **5. ¿Cómo configurar una animación de caída?**
1. En condicional de colisión con obstáculo: `playerAnim.SetBool("Death_b", true);`
2. En mismo condicional: `playerAnim.SetInteger("DeathType_int", 1);`
<img width="1919" height="978" alt="image" src="https://github.com/user-attachments/assets/1c4eafc7-3254-47fd-8a63-e0d3225c54b5" />
<img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/eb72e3a5-7139-47bb-8284-8adf19989887" />

#### **6. ¿Cómo evitar que el jugador salte mientras está inconsciente?**
1. Agregar `&& !gameOver` a la condición del salto
2. Prevenir saltos durante estado de Game Over
<img width="1919" height="992" alt="image" src="https://github.com/user-attachments/assets/56d2e261-f2b0-4370-a176-0fb202229cbf" />


## Lección 3.4: Efectos de sonido y partículas

#### **1. ¿Cómo personalizar una partícula de explosión?**
1. En Course Library > Particles: arrastrar `FX_Explosion_Smoke` a Hierarchy
2. Usar botones Play/Restart/Stop para previsualizar
3. Modificar configuración del Particle System según preferencias
4. Desmarcar "Play on Awake"
5. Arrastrar partícula al jugador como child object
6. Posicionar relativa al jugador
<img width="1919" height="983" alt="image" src="https://github.com/user-attachments/assets/015ff140-6ce1-4201-bb2c-a5b1a4b5f095" />

#### **2. ¿Cómo reproducir la partícula al momento de la colisión?**
1. En PlayerController.cs: declarar `public ParticleSystem explosionParticle;`
2. En Inspector: asignar explosión a variable Explosion Particle
3. En condicional de colisión con obstáculo: `explosionParticle.Play();`
4. Probar y corregir propiedades de partículas
<img width="1919" height="1008" alt="image" src="https://github.com/user-attachments/assets/c8838c61-dfa5-49bb-8e32-1ee90fda775d" />
<img width="1911" height="1014" alt="image" src="https://github.com/user-attachments/assets/70fe933a-412a-403d-ba0c-e522c1414db9" />


#### **3. ¿Cómo agregar una partícula de salpicadura de polvo?**
1. Arrastrar `FX_DirtSplatter` como child object del jugador
2. Reubicar, rotar y editar configuración
3. Declarar `public ParticleSystem dirtParticle;`
4. Asignar en Inspector
5. `dirtParticle.Stop();` cuando jugador salta o choca con obstáculo
6. `dirtParticle.Play();` cuando jugador aterriza en suelo
   <img width="1918" height="1007" alt="Captura de pantalla 2025-10-25 132133" src="https://github.com/user-attachments/assets/b425f542-115d-4414-aad9-d9aebfdc1907" />

<img width="1918" height="991" alt="image" src="https://github.com/user-attachments/assets/3d36f7c0-5049-4e1c-a883-2ca49b6aa227" />

#### **4. ¿Cómo agregar música al objeto de cámara?**
1. Seleccionar Main Camera: `Add Component > Audio Source`
2. En Course Library > Sound: arrastrar clip de música a AudioClip
3. Reducir volumen para mejor mezcla con efectos
4. Marcar casilla "Loop" para reproducción continua
<img width="1919" height="1009" alt="image" src="https://github.com/user-attachments/assets/dd3a762b-181f-48e0-a93b-d05fe2a81488" />

#### **5. ¿Cómo declarar variables para Clips de audio?**
1. En PlayerController.cs: declarar `public AudioClip jumpSound;`
2. Declarar `public AudioClip crashSound;`
3. En Course Library > Sound: arrastrar clips a variables en Inspector
<img width="1915" height="552" alt="image" src="https://github.com/user-attachments/assets/2a5c0a46-6d39-4971-9aa4-de1ddbd5c5e3" />

#### **6. ¿Cómo reproducir clips de audio al saltar y al chocar?**
1. Agregar componente Audio Source al Player
2. Declarar `private AudioSource playerAudio;`
3. Inicializar: `playerAudio = GetComponent<AudioSource>();`
4. En salto: `playerAudio.PlayOneShot(jumpSound, 1.0f);`
5. En colisión: `playerAudio.PlayOneShot(crashSound, 1.0f);`
<img width="1866" height="969" alt="image" src="https://github.com/user-attachments/assets/80179843-eaf3-494e-b318-202e98fafa07" />
<img width="1919" height="1025" alt="image" src="https://github.com/user-attachments/assets/71065673-f479-4e29-8064-506b36cb68eb" />

# VIDEO 


https://github.com/user-attachments/assets/ceae5f60-dfcb-426f-87aa-7d6e3bc34f6e




