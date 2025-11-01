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

#### **5. ¿Cómo agregar puntos cuando se destruyen los objetivos?**
1. En GameManager.cs: cambiar UpdateScore a `public`
2. En Target.cs: crear `private GameManager gameManager;`
3. En Start(): inicializar `gameManager = FindObjectOfType<GameManager>();`
4. En OnMouseDown(): llamar `gameManager.UpdateScore(pointValue);`
5. Eliminar llamada a UpdateScore en SpawnTarget()

#### **6. ¿Cómo agregar un valor de puntos a cada objetivo?**
1. En Target.cs: crear `public int pointValue;`
2. En Inspector de cada Target Prefab: definir Point Value
   - Objetivos buenos: valores positivos variados
   - Objetivo malo: valor negativo
3. En OnMouseDown(): usar `gameManager.UpdateScore(pointValue);`

#### **7. ¿Cómo agregar una partícula de explosión?**
1. En Target.cs: agregar `public ParticleSystem explosionParticle;`
2. En cada Target Prefab: asignar prefab de partículas desde Course Library > Particles
3. En OnMouseDown(): instanciar nuevo prefab de explosión


## 🔗 NAVEGACIÓN
- [📋 Volver al README Principal](../README.md)
- [⬅️ Lección Anterior: Sonidos y Efectos](../unidad-3-Sonidos-y-efectos.md)

---

*🔄 Unidad 5 en progreso - Sistema de destrucción por clic implementado* 
