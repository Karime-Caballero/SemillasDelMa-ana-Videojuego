# Unidad 5: Interfaz de usuario


###  INFORMACIÓN GENERAL
- **Objetivo:** Implementar sistema de salto y generación de obstáculos


# UNIDAD 5: INTERFAZ DE USUARIO

## INFORMACIÓN GENERAL
- **Ubicación:** `tutoriales/unidad-5-Interfaz-de-usuario.md`
- **Objetivo:** Implementar sistema de destrucción por clic y gestión de objetivos

## Lección 5.1: ¿Cómo destruir con un clic?

### SECCIONES DE LA LECCIÓN

#### **1. ¿Cómo crear un proyecto y cambiar la vista a 2D?**
1. Crear proyecto "Prototype 5" vacío en Unity Hub
2. Descargar e importar "Prototype 5 - Starter Files.unitypackage"
3. Abrir escena Prototype 5 y eliminar escena de muestra
4. Hacer clic en ícono 2D en vista de Escena
5. (Opcional) Cambiar textura y color del fondo y bordes
<img width="1919" height="1000" alt="image" src="https://github.com/user-attachments/assets/15808aa1-5e46-44a2-89ad-a5ec1f949570" />

   

#### **2. ¿Cómo crear objetivos buenos y malos?**
1. De Library: arrastrar 3 objetos "buenos" y 1 objeto "malo" a Escena
2. Renombrar como "Good 1", "Good 2", "Good 3" y "Bad 1"
3. Agregar componentes Rigidbody y Box Collider
4. Ajustar colisionadores para que rodeen objetos adecuadamente
5. Crear carpeta Scripts con script "Target.cs"
6. Adjuntar script a los objetivos
7. Crear Prefabs "original Prefabs" y eliminar de Escena
<img width="1919" height="1016" alt="image" src="https://github.com/user-attachments/assets/b48af636-9ec1-463c-b2da-f90424b07132" />

#### **3. ¿Cómo arrojar los objetos al aire de forma aleatoria?**
1. En Target.cs: declarar `private Rigidbody targetRb;`
2. En Start(): inicializar `targetRb = GetComponent<Rigidbody>();`
3. En Start(): agregar impulso hacia arriba multiplicado por velocidad aleatoria
4. Agregar torsión con valores XYZ aleatorios
5. Definir posición con valor X aleatorio


<img width="1919" height="987" alt="image" src="https://github.com/user-attachments/assets/c814d591-9f83-4de4-9f80-45ebee3dcac0" />

<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/ac9bd30b-5173-4ec2-83ab-bb3790b9458d" />

#### **4. ¿Cómo cambiar el código complicado con nuevos métodos?**
1. Declarar variables: `minSpeed`, `maxSpeed`, `maxTorque`, `xRange`, `ySpawnPos`
2. Crear función `Vector3 RandomForce()` y llamarla en Start()
3. Crear función `float RandomTorque()` y llamarla en Start()
4. Crear función `RandomSpawnPos()` que devuelva Vector3 y llamarla en Start()

   <img width="1919" height="1000" alt="image" src="https://github.com/user-attachments/assets/571e9f2e-3400-4316-839e-fd44a07d2598" />


#### **5. ¿Cómo crear una lista de objetos en Game Manager?**
1. Crear objeto vacío "Game Manager"
2. Adjuntar script "GameManager.cs"
3. Declarar `public List<GameObject> targets;`
4. En Inspector: cambiar Size de lista a 4
5. Asignar Prefabs a la lista
<img width="1919" height="935" alt="image" src="https://github.com/user-attachments/assets/8e66814c-bd0e-4f5d-a219-dc3bdd79f86f" />
<img width="1913" height="1016" alt="image" src="https://github.com/user-attachments/assets/59918505-e824-4548-9e1f-ec6146d4ff82" />


#### **6. ¿Cómo crear una corrutina para generar objetos?**
1. Declarar `private float spawnRate;`
2. Crear método `IEnumerator SpawnTarget()`
3. Dentro del método: `while(true)`, esperar 1 segundo
4. Generar índice aleatorio y objetivo aleatorio
5. En Start(): usar `StartCoroutine()` para comenzar generación

   <img width="1915" height="966" alt="image" src="https://github.com/user-attachments/assets/e2963a7b-2e7f-4535-99ea-9a69062abed8" />
   <img width="1913" height="1011" alt="image" src="https://github.com/user-attachments/assets/58521ddb-09de-489b-9220-1213a1cf83d5" />



#### **7. ¿Cómo destruir objetivos con clics y sensores?**
1. En Target.cs: agregar método `private void OnMouseDown() { Destroy(gameObject); }`
2. Agregar método `private void OnTriggerEnter(Collider other) { Destroy(gameObject); }`
<img width="1891" height="986" alt="image" src="https://github.com/user-attachments/assets/434c70f8-2833-4a2a-adb0-4f2e590e4793" />



## Lección 5.2: ¿Cómo monitorizar el puntaje?

### SECCIONES DE LA LECCIÓN

#### **1. ¿Cómo agregar la posición del texto del puntaje en la pantalla?**
1. En Hierarchy: `Create > UI > TextMeshPro text`
2. Si se solicita: hacer clic en "Import TMP Essentials"
3. Renombrar nuevo objeto como "Score Text"
4. Alejar para ver el canvas en vista de Escena
5. Cambiar Anchor Point a esquina superior izquierda
6. En Inspector: cambiar Pos X y Pos Y para esquina superior izquierda
<img width="1919" height="990" alt="image" src="https://github.com/user-attachments/assets/1a3516bd-6231-45ac-954b-dd08189edf03" />

   

#### **2. ¿Cómo editar las propiedades de Score Text?**
1. Cambiar texto a "Score:"
2. Elegir Font Asset apropiado
3. Configurar Style, Size y Vertex Color
4. Asegurar buen contraste con el fondo

   <img width="1919" height="969" alt="image" src="https://github.com/user-attachments/assets/d1e2549c-22f3-492a-806a-67f40a0d69c2" />


#### **3. ¿Cómo inicializar la variable y el texto del puntaje?**
1. En GameManager.cs: agregar `using TMPro;`
2. Declarar `public TextMeshProUGUI scoreText;`
3. Asignar variable en Inspector
4. Crear `private int score;` e inicializar en Start(): `score = 0;`
5. En Start(): `scoreText.text = "Score: " + score;`

   <img width="1919" height="1003" alt="image" src="https://github.com/user-attachments/assets/f143782e-5172-4599-9e56-c0fa2c4c3e09" />


#### **4. ¿Cómo crear un nuevo método UpdateScore?**
1. Crear método `private void UpdateScore(int scoreToAdd)`
2. Mover `scoreText.text = "Score: " + score;` al nuevo método
3. Llamar `UpdateScore(0)` en Start()
4. En UpdateScore(): `score += scoreToAdd;`
5. Llamar `UpdateScore(5)` en SpawnTarget() (temporal)

 <img width="1919" height="999" alt="image" src="https://github.com/user-attachments/assets/0ade129f-07a6-4349-87b4-6a9195032c1f" />

<img width="1919" height="972" alt="image" src="https://github.com/user-attachments/assets/5e267453-7224-479a-9a2c-2276390760db" />

#### **5. ¿Cómo agregar puntos cuando se destruyen los objetivos?**
1. En GameManager.cs: cambiar UpdateScore a `public`
2. En Target.cs: crear `private GameManager gameManager;`
3. En Start(): inicializar `gameManager = FindObjectOfType<GameManager>();`
4. En OnMouseDown(): llamar `gameManager.UpdateScore(pointValue);`
5. Eliminar llamada a UpdateScore en SpawnTarget()

<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/a5abe06a-613a-410d-9aaa-5186f20c356d" />
<img width="1886" height="776" alt="image" src="https://github.com/user-attachments/assets/2cd520f0-bc07-4b9a-a4b4-9b9225ae5c28" />
<img width="1917" height="920" alt="image" src="https://github.com/user-attachments/assets/f15a8468-20d5-4d30-85d1-3d92d8cc2df3" />


#### **6. ¿Cómo agregar un valor de puntos a cada objetivo?**
1. En Target.cs: crear `public int pointValue;`
2. En Inspector de cada Target Prefab: definir Point Value
   - Objetivos buenos: valores positivos variados
   - Objetivo malo: valor negativo
3. En OnMouseDown(): usar `gameManager.UpdateScore(pointValue);`

   <img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/47e8aa8c-0b0d-47a6-8fe7-a11c39e2b268" />
   <img width="1914" height="984" alt="image" src="https://github.com/user-attachments/assets/e4ff8199-6f3c-43ea-a96f-641d248016e8" />



#### **7. ¿Cómo agregar una partícula de explosión?**
1. En Target.cs: agregar `public ParticleSystem explosionParticle;`
2. En cada Target Prefab: asignar prefab de partículas desde Course Library > Particles
3. En OnMouseDown(): instanciar nuevo prefab de explosión

   <img width="1919" height="1008" alt="image" src="https://github.com/user-attachments/assets/994a4d03-5697-4dcb-b42a-545d82257100" />


## Lección 5.3: Game Over

### SECCIONES DE LA LECCIÓN

#### **1. ¿Cómo crear un objeto de texto de Game Over?**
1. Clic derecho en Canvas: `UI > TextMeshPro - Text`
2. Renombrar como "Game Over Text"
3. En Inspector: editar Text, Pos X, Pos Y, Font Asset, Size, Style, Color y Alignment
4. Configurar "Wrapping" a "Disabled"

   
<img width="1919" height="1013" alt="Captura de pantalla 2025-10-31 232934" src="https://github.com/user-attachments/assets/c8002e7f-c743-472d-a6a3-23fd17b78e6c" />

#### **2. ¿Cómo hacer que aparezca el texto de GameOver?**
1. En GameManager.cs: crear `public TextMeshProUGUI gameOverText;`
2. Asignar objeto Game Over en Inspector
3. Desmarcar casilla "Active" para desactivar texto por defecto
4. En Start(): activar texto temporalmente para pruebas
<img width="1919" height="986" alt="Captura de pantalla 2025-10-31 234014" src="https://github.com/user-attachments/assets/c3f48c87-6589-49d4-8c49-0f307d46563d" />
<img width="1918" height="1015" alt="Captura de pantalla 2025-10-31 234031" src="https://github.com/user-attachments/assets/6dbc5471-00d4-4167-8c4e-400a49c8ff9e" />

#### **3. ¿Cómo crear la función GameOver?**
1. Crear función `public void GameOver()`
2. Mover código de activación de texto a esta función
3. En Target.cs: llamar `gameManager.GameOver()` en OnTriggerEnter()
4. Agregar etiqueta "Bad" al objeto malo
5. Agregar condición para solo Game Over si NO es objeto malo
<img width="1918" height="990" alt="image" src="https://github.com/user-attachments/assets/b9a15645-492f-4ab8-85c4-d43cf536ce66" />
<img width="1919" height="986" alt="image" src="https://github.com/user-attachments/assets/548df423-460e-448d-82f5-54086f07a782" />


#### **4. ¿Cómo detener la generación de obstáculos y el puntaje durante un GameOver?**
1. Crear `public bool isGameActive;`
2. En Start(): `isGameActive = true;`
3. En GameOver(): `isGameActive = false;`
4. En corrutina SpawnTarget(): cambiar `while (true)` a `while (isGameActive)`
5. En Target.cs OnMouseDown(): agregar `if (gameManager.isGameActive)`
<img width="1899" height="958" alt="image" src="https://github.com/user-attachments/assets/b2048b79-ad0d-409f-a481-b0a11851f335" />



#### **5. ¿Cómo agregar un botón Reiniciar?**
1. Clic derecho en Canvas: `Create > UI > Button`
2. Renombrar botón como "Restart Button"
3. Temporalmente reactivar texto Game Over para posicionar botón
4. Seleccionar objeto hijo Text y editar para que diga "Restart"
5. Configurar Font, Style y Size del texto

   <img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/b91affbe-9927-4f13-bb69-014d269ee5d6" />


#### **6. ¿Cómo hacer que funcione el botón de reinicio?**
1. En GameManager.cs: agregar `using UnityEngine.SceneManagement;`
2. Crear función `public void RestartGame()`
3. En función: `SceneManager.LoadScene(SceneManager.GetActiveScene().name);`
4. En Inspector del botón: agregar nuevo evento On Click
5. Arrastrar Game Manager y seleccionar `GameManager.RestartGame`
<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/43647412-ae17-4396-8162-ba5e55d201d0" />

#### **7. ¿Cómo mostrar el botón de reinicio durante el fin del juego?**
1. En GameManager.cs: agregar `using UnityEngine.UI;`
2. Declarar `public Button restartButton;`
3. Asignar Restart Button en Inspector
4. Desmarcar casilla "Active" para Restart Button
5. En función GameOver(): activar Restart Button
<img width="1917" height="995" alt="image" src="https://github.com/user-attachments/assets/55963b17-1277-4019-94f9-021ef21a2442" />

# UNIDAD 5: INTERFAZ DE USUARIO

## INFORMACIÓN GENERAL
- **Ubicación:** `tutoriales/unidad-5-Interfaz-de-usuario.md`
- **Objetivo:** Implementar sistema de menú y selección de dificultad

## Lección 5.4: ¿Cuál es la dificultad?

### SECCIONES DE LA LECCIÓN

#### **1. ¿Cómo crear el texto del título y los botones del menú?**
1. Duplicar texto "Game Over" para crear "Title Text"
2. Editar nombre, texto y atributos del título
3. Duplicar "Restart Button" para crear botón "Easy"
4. Editar y duplicar para crear botones "Medium" y "Hard"
<img width="1919" height="992" alt="image" src="https://github.com/user-attachments/assets/c56ce2c9-949a-4e59-ac97-3fd2741d670c" />
<img width="1917" height="1019" alt="image" src="https://github.com/user-attachments/assets/40587d38-8d95-4736-98f8-bb41a2bc42eb" />


#### **2. ¿Cómo agregar un Script DifficultyButton?**
1. En los 3 botones: eliminar funcionalidad RestartGame de On Click
2. Crear nuevo script "DifficultyButton.cs"
3. Adjuntar script a los 3 botones
4. Agregar `using UnityEngine.UI`
5. Crear `private Button button;` e inicializar en Start()

   <img width="1913" height="1017" alt="image" src="https://github.com/user-attachments/assets/b0954cd0-8259-4b20-92b8-c435e6565414" />
<img width="1919" height="724" alt="image" src="https://github.com/user-attachments/assets/cd681e09-c334-4e71-a061-bb74a56c8c4e" />


#### **3. ¿Cómo llamar SetDifficulty al hacer clic en el botón?**
1. Crear función `void SetDifficulty()`
2. Dentro: `Debug.Log(gameObject.name + " was clicked");`
3. Agregar listener del botón para llamar SetDifficulty

<img width="1911" height="845" alt="image" src="https://github.com/user-attachments/assets/2a94603d-8e00-4bd2-8d46-400aaed00210" />
<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/ecec15eb-f877-44c5-a83d-bffa57a68fc3" />

#### **4. ¿Cómo hacer que tus botones inicien el juego?**
1. En GameManager.cs: crear `public void StartGame()`
2. Mover contenido de Start() a StartGame()
3. En DifficultyButton.cs: crear `private GameManager gameManager;`
4. Inicializar en Start()
5. En SetDifficulty(): llamar `gameManager.StartGame()`

<img width="1918" height="915" alt="image" src="https://github.com/user-attachments/assets/0d92ebb2-ede6-4fe1-b08a-978cb9412fcd" />

<img width="1919" height="1019" alt="image" src="https://github.com/user-attachments/assets/2a0a712d-34d8-40a6-9c65-ddafaaf93e0a" />

#### **5. ¿Cómo desactivar la pantalla del título al iniciar el juego?**
1. Crear Empty Object "Title Screen" en Canvas
2. Arrastrar 3 botones y título a Title Screen
3. En GameManager.cs: crear `public GameObject titleScreen;`
4. Asignar en Inspector
5. En StartGame(): desactivar `titleScreen`

   <img width="1914" height="1024" alt="image" src="https://github.com/user-attachments/assets/40411c43-619d-4480-bc2f-66bdb0c7ef3e" />
<img width="1919" height="1009" alt="image" src="https://github.com/user-attachments/assets/e1da3cfc-df6a-4428-8aa5-9c76501df1d2" />


#### **6. ¿Cómo utilizar un parámetro para cambiar la dificultad?**
1. En DifficultyButton.cs: crear `public int difficulty;`
2. En Inspector: asignar Easy=1, Medium=2, Hard=3
3. Agregar parámetro `int difficulty` a StartGame()
4. En StartGame(): `spawnRate /= difficulty;`
5. En SetDifficulty(): pasar `difficulty` a StartGame()

<img width="1914" height="884" alt="image" src="https://github.com/user-attachments/assets/ca9c0b68-0702-4599-b2b9-7f01296c7089" />
<img width="1844" height="949" alt="image" src="https://github.com/user-attachments/assets/64a0e9a6-f7b4-4814-8697-fe67fb093e33" />
<img width="1919" height="974" alt="image" src="https://github.com/user-attachments/assets/f2ee1887-f48c-47f0-82ce-a4d95ca5787e" />

---
# VIDEO 


https://github.com/user-attachments/assets/e36a322f-682b-457b-bcce-76d4a2b28c61


*✅ UNIDAD 5 COMPLETAMENTE FINALIZADA - JUEGO COMPLETO CON INTERFAZ DE USUARIO* 🎮🖥️

## 🔗 NAVEGACIÓN
- [📋 Volver al README Principal](../README.md)
- [⬅️ Lección Anterior: Sonidos y Efectos](../unidad-3-Sonidos-y-efectos.md)

---

*🔄 Unidad 5 en progreso - Sistema de destrucción por clic implementado* 
