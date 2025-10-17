
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



#### **2. ¿Cómo añadir al jugador, los animales y la comida?**
1. Arrastrar material desde Course Library > Materials al suelo
2. Arrastrar a Hierarchy: 1 humano, 3 animales y 1 alimento
3. Renombrar personaje como "Player"
4. Reubicar animales y comida para mejor visibilidad
5. Ajustar escala XYZ de la comida para verla desde arriba



#### **3. ¿Cómo obtener la entrada horizontal del usuario?**
1. Crear carpeta "Scripts" en Assets
2. Crear script "PlayerController" dentro de Scripts
3. Adjuntar script al jugador
4. Definir `public float horizontalInput;`
5. En Update(): `horizontalInput = Input.GetAxis("Horizontal")`
6. Probar funcionamiento en Inspector

   

#### **4. ¿Cómo mover al jugador de izquierda a derecha?**
1. Definir `public float speed = 10.0f;`
2. En Update(): desplazar jugador basado en horizontalInput y speed



#### **5. ¿Cómo mantener al jugador dentro de los límites?**
1. En Update(): escribir condicional para verificar posición X izquierda
2. Si posición X es menor que valor dado, fijar posición X



#### **6. ¿Cómo limpiar el código y las variables?**
1. Repetir proceso para límite derecho de pantalla
2. Definir variable `xRange` y reemplazar valores hardcodeados
3. Agregar comentarios al código

