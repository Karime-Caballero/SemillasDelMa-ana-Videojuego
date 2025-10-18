
# UNIDAD 2: JUGABILIDAD BÁSICA
# Lección 2.1: Posición del jugador

##  INFORMACIÓN GENERAL
- **Ubicación:** `tutoriales/unidad-2-Jugabilidad-basica.md`
- **Estado:**  En Progreso
- **Objetivo:** Implementar movimiento del jugador y límites de pantalla

##  SECCIONES DE LA LECCIÓN

#### **1. ¿Cómo crear un proyecto nuevo para el prototipo 2?**
1. Abrir Unity Hub y crear proyecto "Prototype 2" vacío
2. Descargar e importar `Prototype 2 Starter Files.unitypackage`
3. Abrir escena del prototipo 2 desde ventana Project
4. Eliminar escena de muestra
5. Cambiar layout por defecto al layout personalizado

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/ee11ac42-efb2-4860-9fde-4028efc96360" />


#### **2. ¿Cómo añadir al jugador, los animales y la comida?**
1. Arrastrar material desde Course Library > Materials al suelo
2. Arrastrar a Hierarchy: 1 humano, 3 animales y 1 alimento
3. Renombrar personaje como "Player"
4. Reubicar animales y comida para mejor visibilidad
5. Ajustar escala XYZ de la comida para verla desde arriba
<img width="1915" height="1004" alt="image" src="https://github.com/user-attachments/assets/652eb41d-dcc3-48fc-85a6-2fc8534299f9" />


#### **3. ¿Cómo obtener la entrada horizontal del usuario?**
1. Crear carpeta "Scripts" en Assets
2. Crear script "PlayerController" dentro de Scripts
3. Adjuntar script al jugador
4. Definir `public float horizontalInput;`
5. En Update(): `horizontalInput = Input.GetAxis("Horizontal")`
6. Probar funcionamiento en Inspector

<img width="1919" height="983" alt="image" src="https://github.com/user-attachments/assets/15054469-8477-4ecf-ad8d-4e59db5a9da4" />
<img width="1918" height="1022" alt="image" src="https://github.com/user-attachments/assets/2d32f44c-09f4-421f-a7f3-59e99cc932e5" />


#### **4. ¿Cómo mover al jugador de izquierda a derecha?**
1. Definir `public float speed = 10.0f;`
2. En Update(): desplazar jugador basado en horizontalInput y speed

<img width="1919" height="1071" alt="image" src="https://github.com/user-attachments/assets/5f750994-9c9c-403a-b460-3f67e21d7dc4" />
<img width="1729" height="926" alt="image" src="https://github.com/user-attachments/assets/d2ae9a52-dd59-461b-a645-801d7f7bef66" />


#### **5. ¿Cómo mantener al jugador dentro de los límites?**
1. En Update(): escribir condicional para verificar posición X izquierda
2. Si posición X es menor que valor dado, fijar posición X
<img width="1671" height="892" alt="image" src="https://github.com/user-attachments/assets/fcc2115c-3988-4bf4-a424-1e4125223f83" />
<img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/8deb8d2d-10af-4f3a-8cae-678859e02980" />



#### **6. ¿Cómo limpiar el código y las variables?**
1. Repetir proceso para límite derecho de pantalla
2. Definir variable `xRange` y reemplazar valores hardcodeados
3. Agregar comentarios al código

<img width="1712" height="900" alt="image" src="https://github.com/user-attachments/assets/201a2b5d-e84d-481c-9007-31a1e96c6947" />
<img width="1919" height="1019" alt="image" src="https://github.com/user-attachments/assets/e0e4365e-0d1e-49c2-8ff0-9ae5d83fed17" />


# Lección 2.2: Comida voladora
##  SECCIONES DE LA LECCIÓN

#### **1. ¿Cómo hacer que el proyectil vuele hacia adelante?**
1. Crear nuevo Script llamado "MoveForward"
2. Adjuntar script al objeto Food
3. Definir `public float speed;` como variable
4. En Update(): `transform.Translate(Vector3.forward * Time.deltaTime * speed);`
5. Guardar y establecer variable speed en Inspector
6. Probar funcionamiento
<img width="1711" height="926" alt="image" src="https://github.com/user-attachments/assets/39da7439-762d-4e21-ba9c-2cce38605108" />
<img width="1919" height="1006" alt="image" src="https://github.com/user-attachments/assets/c3101947-9726-4a41-b056-35a4072242c8" />


#### **2. ¿Cómo convertir el proyectil en un Prefab?**
1. Crear carpeta "Prefabs" en Project
2. Arrastrar comida y seleccionar "Original Prefab"
3. En PlayerController.cs: definir `public GameObject projectilePrefab;`
4. Seleccionar jugador en Hierarchy
5. Arrastrar prefab de proyectil a "Projectile Prefab" en Inspector
6. Probar arrastrando proyectil a escena durante ejecución

   <img width="1919" height="1030" alt="image" src="https://github.com/user-attachments/assets/eb50a42e-fd65-4838-b42f-e7deaf2d16cb" />
<img width="1707" height="911" alt="image" src="https://github.com/user-attachments/assets/f8cb4a1d-77e4-4b5a-84e2-60b264de1528" />


#### **3. ¿Cómo probar la pulsación de la barra espaciadora?**
1. En PlayerController.cs, en Update():
2. Agregar condicional: `if (Input.GetKeyDown(KeyCode.Space)) {`
3. Dentro del condicional: `// Launch a projectile from the player`

<img width="1713" height="912" alt="image" src="https://github.com/user-attachments/assets/3762ef7c-54ba-4756-98e9-d91374e1a95d" />


#### **4. ¿Cómo lanzar un proyectil cuando se pulsa la barra espaciadora?**
1. En el condicional del espacio:
2. Usar `Instantiate()` para generar proyectil
3. Especificar posición del jugador y rotación del prefab

<img width="1720" height="900" alt="image" src="https://github.com/user-attachments/assets/667e6825-94dc-471e-969d-168a30e121a5" />
<img width="1919" height="1027" alt="image" src="https://github.com/user-attachments/assets/e2031a82-4e50-4681-8277-b2713e687521" />



#### **5. ¿Cómo convertir los animales en Prefabs?**
1. Rotar todos los animales 180 grados en eje Y
2. Seleccionar los tres animales en Hierarchy
3. Agregar componente "Move Forward"
4. Editar valores speed y probar
5. Arrastrar animales a carpeta Prefabs como "Original Prefab"
6. Probar arrastrando prefabs a escena durante juego

<img width="1919" height="1026" alt="image" src="https://github.com/user-attachments/assets/a7ccff2c-c46b-4cc4-8931-8284c62a4b1e" />
<img width="1919" height="1061" alt="image" src="https://github.com/user-attachments/assets/f29e030d-19fc-457e-9830-e5624491a33d" />
<img width="1919" height="1048" alt="image" src="https://github.com/user-attachments/assets/9be2eef6-7275-4862-9a50-77c4dc78b698" />




#### **6. ¿Cómo destruir los proyectiles fuera de la pantalla?**
1. Crear Script "DestroyOutOfBounds"
2. Aplicar script al proyectil
3. Agregar `private float topBound = 30;`
4. Escribir código: `if (transform.position.z > topBound) { Destroy(gameObject); }`
5. En Inspector, usar "Overrides" → "Apply all" para aplicar al Prefab

<img width="1919" height="1012" alt="image" src="https://github.com/user-attachments/assets/6ad32b0c-4508-40bf-96f5-fa2ad08f00aa" />
<img width="1706" height="915" alt="image" src="https://github.com/user-attachments/assets/789cb6ac-8182-46a4-babc-6879a9c3e733" />


#### **7. ¿Cómo destruir los animales fuera de la pantalla?**
1. Crear condicional `else if` para verificar `lowerBound`
2. Aplicar script a todos los animales
3. Usar "Override" en los Prefabs de animales
<img width="1919" height="1041" alt="image" src="https://github.com/user-attachments/assets/43cb9d40-e787-409d-996e-35f615b719e5" />
<img width="1734" height="925" alt="image" src="https://github.com/user-attachments/assets/23af1894-f05c-434d-9470-656b1ff21be0" />



# Lección 2.3: Estampida de animales aleatorios
##  SECCIONES DE LA LECCIÓN

#### **1. Crea un gestor de generación**
1. En Hierarchy: crear Empty Object llamado "SpawnManager"
2. Crear script "SpawnManager" y adjuntarlo al objeto
3. Definir `public GameObject[] animalPrefabs;`
4. En Inspector: cambiar tamaño del array según cantidad de animales
5. Arrastrar prefabs de animales desde Project (no Hierarchy) a los espacios del array

<img width="1722" height="931" alt="image" src="https://github.com/user-attachments/assets/40373fef-4fa3-4316-83ea-52947ff7cdd3" />
<img width="1916" height="1027" alt="image" src="https://github.com/user-attachments/assets/4f75013f-05c1-4f7f-bba7-1d79cbaaedef" />


#### **2. Genera un animal cuando se pulsa la tecla S**
1. En Update(): crear condicional `if (Input.GetKeyDown(KeyCode.S))`
2. Definir `public int animalIndex;`
3. Usar `Instantiate()` con animalPrefabs[animalIndex]
4. Probar editando animalIndex en Inspector
<img width="1919" height="1040" alt="image" src="https://github.com/user-attachments/assets/95cb7c34-18be-48bc-bf8a-3f1b4976cbff" />
<img width="1735" height="919" alt="image" src="https://github.com/user-attachments/assets/36bca482-2adf-46fc-8ef9-1747674236f2" />

#### **3. Generar animales aleatorios desde el arreglo**
1. En condicional de tecla S: generar índice aleatorio
2. `int animalIndex = Random.Range(0, animalPrefabs.Length);`
3. Eliminar variable global animalIndex (usar solo localmente)
4. Probar generación aleatoria

   <img width="1919" height="1023" alt="image" src="https://github.com/user-attachments/assets/e368c71d-8332-4023-a6d2-7cb6722c4923" />
   <img width="1717" height="921" alt="image" src="https://github.com/user-attachments/assets/200bad87-5042-40ad-a059-2dcb233f223f" />


#### **4. Establece al azar la ubicación de la generación**
1. Reemplazar posición X fija por `Random.Range(-20, 20)`
2. Crear variable local `Vector3 spawnPos`
3. En parte superior de clase: crear `private float spawnRangeX` y `spawnPosZ`
4. Usar variables para definir rango de spawn
<img width="1716" height="899" alt="image" src="https://github.com/user-attachments/assets/6380d89d-7eee-4a85-9eb8-369b1df5584c" />
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/eeb1dae5-fd1a-4e21-82da-ba3250bbea12" />


#### **5. Cambia la perspectiva de la cámara**
1. En Scene View: alternar entre Perspective e Isometric
2. Seleccionar cámara principal
3. En componente Camera: cambiar Projection de "Perspective" a "Orthographic"
4. Ajustar tamaño de cámara orthographic según necesidad
<img width="1919" height="1019" alt="image" src="https://github.com/user-attachments/assets/0376df67-540a-4c07-9a83-5ae15d781c6e" />

# Lección 2.4: Decisiones de colisiones
##  SECCIONES DE LA LECCIÓN

#### **1. Haz un nuevo método para generar animales**
1. En SpawnManager.cs: crear función `void SpawnRandomAnimal() {}` debajo de Update()
2. Cortar y pegar código del condicional de tecla S a la nueva función
3. Llamar `SpawnRandomAnimal();` cuando se presione tecla S

   
<img width="1716" height="945" alt="Captura de pantalla 2025-10-18 002401" src="https://github.com/user-attachments/assets/87333b2f-6ddd-4a15-a3f3-83e4bb24ba75" />

#### **2. Genera animales en intervalos de tiempo**
1. En Start(): usar `InvokeRepeating()` para generar animales automáticamente
2. Eliminar condicional de tecla S
3. Definir `private float startDelay` y `spawnInterval`
4. Probar y ajustar valores de las variables

   <img width="1715" height="925" alt="image" src="https://github.com/user-attachments/assets/07c90859-5d39-49ac-a8fd-4731aefcf17e" />


#### **3. Agrega un componente Collider y Trigger**
1. Abrir prefab de animal: `Add Component > Box Collider`
2. Hacer clic en "Edit Collider" y ajustar manillas para abarcar el objeto
3. Marcar casilla "Is Trigger"
4. Repetir proceso en todos los animales y el proyectil
5. Agregar `RigidBody` al proyectil y desmarcar "Use Gravity"

   <img width="1915" height="1074" alt="image" src="https://github.com/user-attachments/assets/a6aeb4cf-3938-44f8-ad8c-815df0447dcd" />


#### **4. Destruye objetos al colisionar**
1. Crear script "DetectCollisions.cs"
2. Agregar script a cada animal prefab
3. En script: agregar función `OnTriggerEnter()` usando autocomplete
4. Dentro de función: `Destroy(gameObject);` y `Destroy(other.gameObject);`
5. Probar colisiones

   <img width="1716" height="918" alt="image" src="https://github.com/user-attachments/assets/43645063-c769-4440-b5eb-a94efbd9ccb2" />
   <img width="1916" height="1023" alt="image" src="https://github.com/user-attachments/assets/307d434d-530a-43d0-b821-60289e05c0a1" />



#### **5. Desencadena un mensaje de «Game Over»**
1. En DestroyOutOfBounds.cs: en condicional de límite inferior
2. Agregar: `Debug.Log("Game Over!");`
3. Limpiar código con comentarios
4. Usar formato de documento en Visual Studio para corrección de sangría

   <img width="1710" height="920" alt="image" src="https://github.com/user-attachments/assets/6cb08fc6-7e14-45f5-993c-c5fab85e52fc" />
   <img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/c3c89bd8-a979-4a52-9b8c-7eec694a3237" />
   <img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/54a21954-1826-49fc-8627-68245db9e60c" />

#VIDEO DE EVIDENCIA

https://github.com/user-attachments/assets/b202289f-2fc7-45ab-836d-54ba2756ccca



