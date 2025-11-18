# 🧪 QA API Technical Test — Postman + Swagger Petstore

Este repositorio contiene la solución completa al ejercicio técnico de QA orientado a pruebas de API utilizando Postman y la API pública Swagger Petstore.  
Incluye generación dinámica de datos, uso de variables, validaciones automatizadas y ejemplos de respuestas para distintos endpoints.

---

## 📁 Contenido del repositorio

### **📌 Colección de Postman**
`Petstore.postman_collection.json`  
Contiene todas las requests necesarias para completar los 5 casos de prueba del ejercicio:

1. **Create User 1047**  
   - POST `/user`  
   - Script pre-request que genera datos dinámicos (email, password, phone).  
   - Uso de variables de entorno y globales.

2. **Get User by Username**  
   - GET `/user/{{username}}`  
   - Utiliza la variable global creada automáticamente en el caso 1.  
   - Recupera el usuario recién creado.

3. **Find pets by status**  
   - GET `/pet/findByStatus`  
   - Example responses guardados para:  
     - `available`  
     - `pending`  
     - `sold`  
   - Se documenta el comportamiento real de la API (status inválido devuelve `200 []`).

4. **Update User**  
   - PUT `/user/{{username}}`  
   - Actualiza password y teléfono usando variables `updatedPassword` y `updatedPhone`.

5. **Get User (with full automated tests)**  
   - GET `/user/{{username}}`  
   - Contiene todos los tests automatizados:  
     - Status code  
     - Formato JSON  
     - Validación de propiedades  
     - Validación de tipos  
     - Comparación con variables de entorno  
     - Validación de valores actualizados  
     - Tiempo de respuesta  
     - Verificación de propiedades inesperadas  

---

### **📌 Entorno de Postman**
`PetStore.postman_environment.json`  
Incluye todas las variables necesarias para ejecutar la colección:

- host  
- userId  
- username  
- firstName  
- lastName  
- email  
- password  
- phone  
- userStatus  
- updatedPassword  
- updatedPhone  

---

## ▶️ Cómo ejecutar la colección

1. Abrir **Postman**  
2. Importar:
   - `Petstore.postman_collection.json`
   - `PetStore.postman_environment.json`
3. Seleccionar el entorno **PetStore**
4. Ejecutar las requests en este orden:
   1. *Create User 1047*
   2. *Get user maricarmen_perez*
   3. *Find pets (findByStatus)*
   4. *Update user 1047*
   5. *Validate user (Tests)*  
        5.1 Revisar la pestaña **Test Results** de la última request
