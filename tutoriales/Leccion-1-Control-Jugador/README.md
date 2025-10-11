# Create with Code EL CONTROL DEL JUGADOR

#  UNIDAD 1: EL CONTROL DEL JUGADOR

##  INFORMACIÓN GENERAL
- **Ubicación:** `tutoriales/Leccion-1-Control-Jugador/`
- **Estado:** Completado
- **Duración Total:** 4 Lecciones - 240 minutos
- **Motor:** Unity 3D
- **Lenguaje:** C#

- 
## 1.1 START YOUR 3D ENGINES

### **Step 1: Make a course folder and new project**
- Crear carpeta "Create with Code" en el escritorio
- Abrir Unity Hub y crear nuevo proyecto 3D
- Nombrar proyecto "Prototype 1"
- Configurar ubicación en la carpeta del curso


  <img width="1511" height="787" alt="image" src="https://github.com/user-attachments/assets/6f59756d-8f54-4dd1-955e-637baa4454d7" />


### **Step 2: Import assets and open Prototype 1**
- Descargar e importar `Prototype-1_Starter-Files.unitypackage`
- Abrir escena Prototype 1 desde Assets > Scenes
- Eliminar Sample Scene


<img width="1383" height="707" alt="image" src="https://github.com/user-attachments/assets/7dde3340-7067-47ec-9b35-4cbdd5bacc78" />

### **Step 3: Add your vehicle to the scene**
- Arrastrar vehículo desde Assets > Course Library > Vehicles
- Usar tecla **F** para enfocar en el vehículo
- Navegación 3D: 
  - Click derecho + WASD para volar
  - Rueda del mouse para zoom
  - Alt + click para rotar
 
    <img width="1383" height="781" alt="image" src="https://github.com/user-attachments/assets/4eb3cead-26e1-461a-8dd1-1a82c5e9311d" />


### **Step 4: Add an obstacle and reposition it**
- Agregar obstáculo desde Course Library > Obstacles
- Resetear posición en Inspector
- Configurar posición XYZ: (0, 0, 25)
- Renombrar objetos en Hierarchy: "Vehicle" y "Obstacle"
<img width="1379" height="712" alt="image" src="https://github.com/user-attachments/assets/1d2ebfb3-90de-4e6f-ab0f-46a5f5dfb716" />


### **Step 5: Locate your camera and run the game**
- Seleccionar cámara principal y presionar **F**
- Ejecutar juego con botón Play (Ctrl/Cmd + P)
- Entender diferencia entre Game View y Scene View

  <img width="1378" height="731" alt="image" src="https://github.com/user-attachments/assets/76c18e3e-1a7a-4370-9756-a73336a2d35f" />


### **Step 6: Move the camera behind the vehicle**
- Usar herramientas Move y Rotate
- Posicionar cámara detrás del vehículo
- Usar Ctrl/Cmd para movimiento por unidades enteras

  <img width="751" height="559" alt="image" src="https://github.com/user-attachments/assets/e0fb0d50-42d0-467e-9b59-7b8801b284d3" />
  <img width="814" height="405" alt="image" src="https://github.com/user-attachments/assets/74275cc9-d53c-4e14-b9bb-35238bc202be" />



### **Step 7: Customize the interface layout**
- Cambiar layout de "Default" a "Tall"
- Mover Game View debajo de Scene View
- Configurar Project Window a "One-column layout"
- Guardar layout personalizado como "My Layout"

  <img width="1066" height="672" alt="image" src="https://github.com/user-attachments/assets/ea115b13-654b-41d1-a2ec-fceb266e19f4" />

-

## 1.2 PEDAL TO THE METAL

### **Step 1: Create and apply your first script**
1. En Project window: `Right-click > Create > Folder` nombrado "Scripts"
2. En carpeta "Scripts": `Right-click > Create > C# Script` nombrado "PlayerController"
3. Arrastrar script al objeto Vehicle
4. Verificar en Inspector que se agregó como Componente

<img width="1537" height="801" alt="image" src="https://github.com/user-attachments/assets/af5e554a-94bd-4c96-ad7c-03b992297931" />


### **Step 2: Add a comment in the Update() method**
1. Doble-click en script para abrir en Visual Studio
2. En método `Update()`, agregar comentario: `// Move the vehicle forward`

<img width="1450" height="663" alt="image" src="https://github.com/user-attachments/assets/af814da7-d313-49f6-906d-76209fa78ec8" />


### **Step 3: Give the vehicle a forward motion**
1. Escribir `transform.tr` y seleccionar Translate del autocomplete
2. Agregar parámetros `(0, 0, 1)` y punto y coma `;`
3. Presionar `Ctrl/Cmd + S` para guardar
4. Ejecutar juego para probar

<img width="1638" height="700" alt="image" src="https://github.com/user-attachments/assets/ad402fc4-c73b-406f-9171-cebfe22b2b9c" />

### **Step 4: Use a Vector3 to move forward**
1. Eliminar `0, 0, 1` y reemplazar con `Vector3.forward` usando autocomplete

<img width="1541" height="719" alt="image" src="https://github.com/user-attachments/assets/3d7b47a3-c04a-4486-ac7e-65ec62993c05" />

### **Step 5: Customize the vehicle's speed**
1. Agregar `* Time.deltaTime` y probar
2. Agregar `* 20` y probar

<img width="1544" height="730" alt="image" src="https://github.com/user-attachments/assets/7b274e0c-f534-4f8f-bbde-d56169062f43" />

### **Step 6: Add RigidBody components to objects**
1. Seleccionar Vehicle > `Add Component > RigidBody`
2. Seleccionar Obstacle > `Add Component > RigidBody`
3. En propiedades RigidBody, aumentar mass a valores reales en kilogramos
4. Probar colisiones

<img width="1548" height="759" alt="image" src="https://github.com/user-attachments/assets/bdf8a60a-99cf-41d6-bcbf-351b7e4e48f8" />


### **Step 7: Duplicate and position the obstacles**
1. Arrastrar obstacle al final de la lista en Hierarchy
2. Presionar `Ctrl/Cmd + D` para duplicar y mover en eje Z
3. Repetir para crear más obstacles
4. Seleccionar múltiples obstacles con `Ctrl + Click` y duplicar

<img width="1541" height="796" alt="image" src="https://github.com/user-attachments/assets/49e8093f-d613-4c85-8650-2398750d3966" />

-
## 1.3 High Speed Chase

### **Step 1: Add a speed variable for your vehicle**
1. En PlayerController.cs, agregar `public float speed = 5.0f;` al inicio de la clase
2. Reemplazar el valor de velocidad en el método Translate con la variable speed
3. Guardar script y editar el valor de speed en el Inspector para ajustar velocidad


<img width="1547" height="753" alt="image" src="https://github.com/user-attachments/assets/f9a3c8b3-f149-443a-ad3d-349e19b15e5b" />
<img width="1543" height="805" alt="image" src="https://github.com/user-attachments/assets/178556a6-5598-4e87-b186-b47071f4588c" />


### **Step 2: Create a new script for the camera**
1. Crear nuevo script C# llamado "FollowPlayer" y asignarlo a la cámara
2. Agregar `public GameObject player;` al inicio del script
3. Seleccionar Main Camera y arrastrar el objeto player a la variable player en el Inspector
4. En Update(), asignar la posición de la cámara a la posición del player

<img width="1548" height="718" alt="image" src="https://github.com/user-attachments/assets/3d86d24a-739e-4a23-a1e5-4c9af9bf7323" />
<img width="1553" height="748" alt="image" src="https://github.com/user-attachments/assets/b5cf129c-80ab-4ec9-ac7d-10258b44e220" />

### **Step 3: Add an offset to the camera position**
1. En el método Update agregar `+ new Vector3(0, 5, -7)` a la posición
2. Probar el resultado

<img width="1549" height="754" alt="image" src="https://github.com/user-attachments/assets/1f5c5dfc-2a9a-4d43-9308-2eaeca9a250b" />
<img width="1548" height="811" alt="image" src="https://github.com/user-attachments/assets/b8c11506-5450-4efb-a968-01c25f17f889" />

### **Step 4: Make the offset into a Vector3 variable**
1. Declarar `private Vector3 offset;` al inicio de FollowPlayer.cs
2. Copiar el código `new Vector3(0, 5, -7)` y asignarlo a la variable offset
3. Reemplazar el código original con la variable offset
4. Probar y guardar


<img width="1548" height="770" alt="image" src="https://github.com/user-attachments/assets/d4a2131d-b62c-4e48-92f4-8c4130e8268d" />
<img width="1544" height="790" alt="image" src="https://github.com/user-attachments/assets/bbcefcc4-ffde-4401-b861-3b8cf8e5d2fd" />


### **Step 5: Smooth the Camera with LateUpdate**
1. Probar el prototipo para notar el movimiento brusco de la cámara
2. En FollowPlayer.cs, reemplazar Update() con LateUpdate()
3. Guardar y probar para verificar suavizado de movimiento

<img width="1544" height="769" alt="image" src="https://github.com/user-attachments/assets/906f961c-9bdd-4148-865b-eb66c4d503bb" />

### **Step 6: Edit the playmode tint color**
1. Ir a Edit > Preferences (Windows) o Unity > Preferences (Mac)
2. En menú izquierdo, elegir Colors y editar "Playmode tint" con color sutil
3. Probar el proyecto y cerrar preferencias

<img width="1552" height="805" alt="image" src="https://github.com/user-attachments/assets/aae6d8b5-c3fd-44fd-979e-09fc55735255" />


## 1.3 High Speed Chase

### **Step 1: Allow the vehicle to move left/right**
1. En PlayerController.cs, agregar `public float turnSpeed;` al inicio de la clase
2. En Update(), agregar `transform.Translate(Vector3.right * Time.deltaTime * turnSpeed);`
3. Ejecutar juego y usar el slider de turnSpeed en el Inspector para mover el vehículo izquierda/derecha
<img width="1546" height="712" alt="image" src="https://github.com/user-attachments/assets/1dfc9432-3ecc-4071-8194-e2681dda0a6d" />
<img width="1545" height="867" alt="image" src="https://github.com/user-attachments/assets/1ae4db48-4d18-445b-8956-bf30c5349f50" />


### **Step 2: Base left/right movement on input**
1. Ir a Edit > Project Settings > Input Manager y explorar los ejes de input
2. En PlayerController.cs, agregar `public float horizontalInput;`
3. En Update(), asignar `horizontalInput = Input.GetAxis("Horizontal");`
4. Agregar variable horizontalInput al método Translate de movimiento lateral
5. En Inspector, editar turnSpeed y speed variables para ajustar sensibilidad
<img width="1553" height="817" alt="image" src="https://github.com/user-attachments/assets/7ea2c361-f47c-4962-9f50-f8fab00ea5d1" />
<img width="1549" height="695" alt="image" src="https://github.com/user-attachments/assets/acb906cd-c039-4dfd-8823-24df97a89c7a" />
<img width="1557" height="755" alt="image" src="https://github.com/user-attachments/assets/19ac338c-b104-4dd8-85e4-ecf9468eb4c4" />

### **Step 3: Take control of the vehicle speed**
1. Declarar `public float forwardInput;`
2. En Update(), asignar `forwardInput = Input.GetAxis("Vertical");`
3. Agregar variable forwardInput al método Translate de movimiento forward
4. Probar que el vehículo puede moverse hacia adelante y atrás

<img width="1546" height="727" alt="image" src="https://github.com/user-attachments/assets/18350d0c-67d7-49bf-a849-21cd8df3cf49" />
<img width="1548" height="760" alt="image" src="https://github.com/user-attachments/assets/2a8c86b7-3ab8-46ef-9d2d-5842b059782d" />

### **Step 4: Make vehicle rotate instead of slide**
1. En Update(), llamar `transform.Rotate(Vector3.up, horizontalInput)`
2. Eliminar la línea de código que translate Right
3. Agregar `* turnSpeed * Time.deltaTime` al método Rotate
4. Probar que el vehículo ahora rota en lugar de deslizarse

<img width="1550" height="806" alt="image" src="https://github.com/user-attachments/assets/1c6bb14f-cd66-479b-9bbe-a5f6b98fdad7" />

### **Step 5: Clean your code and hierarchy**
1. En Hierarchy: `Right-click > Create Empty` y renombrar "Obstacles"
2. Arrastrar todos los obstacles dentro del objeto Obstacles
3. Inicializar variables con valores en PlayerController
4. Hacer variables privadas (excepto player variables)
5. Agregar comentarios `//` a cada sección del código

<img width="1549" height="726" alt="image" src="https://github.com/user-attachments/assets/75f4aa6d-d432-4076-90e7-c66a8bd0cb86" />

#Video de evidencia



