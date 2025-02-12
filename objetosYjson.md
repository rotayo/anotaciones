# 📌 Objetos y JSON en JavaScript

## 🏗️ Creación de Objetos en JavaScript
En JavaScript, los objetos son estructuras clave-valor que permiten almacenar datos de manera organizada. Se pueden crear de varias maneras.

### 🔹 Sintaxis de Objeto Literal
```javascript
let persona = {
    nombre: "Juan",
    edad: 30,
    ciudad: "Madrid"
};
```

### 🔹 Usando `new Object()`
```javascript
let persona = new Object();
persona.nombre = "Juan";
persona.edad = 30;
persona.ciudad = "Madrid";
```

### 🔹 Con una Función Constructora
```javascript
function Persona(nombre, edad, ciudad) {
    this.nombre = nombre;
    this.edad = edad;
    this.ciudad = ciudad;
}
let persona1 = new Persona("Juan", 30, "Madrid");
```

### 🔹 Usando Clases (EcmaScript6+)
```javascript
class Persona {
    constructor(nombre, edad, ciudad) {
        this.nombre = nombre;
        this.edad = edad;
        this.ciudad = ciudad;
    }
}
let persona2 = new Persona("Juan", 30, "Madrid");
```

---

## 📌 JSON (JavaScript Object Notation)
JSON es un formato de texto ligero para el intercambio de datos. Se basa en la estructura de los objetos de JavaScript.

### 🔹 Sintaxis JSON
```json
{
    "nombre": "Juan",
    "edad": 30,
    "ciudad": "Madrid"
}
```

### 🔹 Diferencia entre Objeto JavaScript y JSON
- Un objeto JavaScript puede contener funciones y referencias a otros objetos.
- JSON solo admite datos primitivos (`string`, `number`, `boolean`, `null`), objetos y arreglos.

---

## 📌 Convertir Objetos a JSON y Viceversa

### 🔹 `JSON.stringify()` - Convertir Objeto a JSON
```javascript
let persona = {
    nombre: "Juan",
    edad: 30,
    ciudad: "Madrid"
};

let jsonString = JSON.stringify(persona);
console.log(jsonString); // '{"nombre":"Juan","edad":30,"ciudad":"Madrid"}'
```

### 🔹 `JSON.parse()` - Convertir JSON a Objeto
```javascript
let jsonString = '{"nombre":"Juan","edad":30,"ciudad":"Madrid"}';
let personaObjeto = JSON.parse(jsonString);
console.log(personaObjeto.nombre); // Juan
```

---

## 📌 JSON en APIs
JSON es el formato más común para enviar y recibir datos en aplicaciones web. Ejemplo de `fetch()` con JSON:
```javascript
fetch('https://jsonplaceholder.typicode.com/users/1')
    .then(response => response.json())
    .then(data => console.log(data));
```

---

✅ Ahora tienes una guía completa sobre objetos y JSON en JavaScript. ¡A programar! 🚀

