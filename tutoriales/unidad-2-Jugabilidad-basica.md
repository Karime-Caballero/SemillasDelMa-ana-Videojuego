
# UNIDAD 2: JUGABILIDAD BÁSICA

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

