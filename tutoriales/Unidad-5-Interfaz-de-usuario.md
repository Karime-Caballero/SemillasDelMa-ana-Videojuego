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

#### **6. ¿Cómo crear una corrutina para generar objetos?**
1. Declarar `private float spawnRate;`
2. Crear método `IEnumerator SpawnTarget()`
3. Dentro del método: `while(true)`, esperar 1 segundo
4. Generar índice aleatorio y objetivo aleatorio
5. En Start(): usar `StartCoroutine()` para comenzar generación

#### **7. ¿Cómo destruir objetivos con clics y sensores?**
1. En Target.cs: agregar método `private void OnMouseDown() { Destroy(gameObject); }`
2. Agregar método `private void OnTriggerEnter(Collider other) { Destroy(gameObject); }`


´´´´
##  CONCEPTOS IMPLEMENTADOS

### **Nuevas Funcionalidades:**
- ✅ Sistema 2D completo
- ✅ Objetivos buenos y malos diferenciados
- ✅ Física aleatoria de lanzamiento
- ✅ Generación continua por corrutinas
- ✅ Destrucción por clic del mouse
- ✅ Detección de salida de pantalla

### **Nuevos Conceptos:**
- ✅ Vista 2D en Unity
- ✅ Listas de GameObjects
- ✅ Corrutinas para timing
- ✅ OnMouseDown() para input
- ✅ OnTriggerEnter() para detección
- ✅ Física con torque aleatorio

## 🔗 NAVEGACIÓN
- [📋 Volver al README Principal](../README.md)
- [⬅️ Lección Anterior: Sonidos y Efectos](../unidad-3-Sonidos-y-efectos.md)

---

*🔄 Unidad 5 en progreso - Sistema de destrucción por clic implementado* 🎯
