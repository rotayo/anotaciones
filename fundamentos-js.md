# Variables, Arreglos y Bucles en JavaScript vs Java vs C#

## 📌 Variables
Las variables almacenan datos y pueden cambiar de valor en el tiempo de ejecución. La declaración de variables varía entre **JavaScript**, **Java** y **C#**.

### **JavaScript**
En JavaScript, las variables pueden declararse con `var`, `let` o `const`.
```javascript
let nombre = "Juan";  // Variable mutable
const edad = 25;       // Variable inmutable
var ciudad = "Madrid"; // No recomendado (funciona similar a let, pero con hoisting)
```

### **Java**
Java es un lenguaje tipado, lo que significa que se debe especificar el tipo de variable.
```java
String nombre = "Juan";
int edad = 25;
final String ciudad = "Madrid"; // `final` hace que la variable sea inmutable
```

### **C#**
C# también es fuertemente tipado y usa `var` para inferencia de tipos.
```csharp
string nombre = "Juan";
int edad = 25;
const string ciudad = "Madrid"; // `const` indica que no puede cambiar
```
---
## 📌 Arreglos
Los arreglos almacenan múltiples valores en una sola variable. 

### **JavaScript**
```javascript
let numeros = [1, 2, 3, 4, 5];
numeros.push(6); // Agregar un elemento
console.log(numeros[0]); // Acceder al primer elemento
```

### **Java**
```java
int[] numeros = {1, 2, 3, 4, 5};
numeros[0] = 10; // Modificar elemento
System.out.println(numeros[0]);
```

### **C#**
```csharp
int[] numeros = {1, 2, 3, 4, 5};
numeros[0] = 10;
Console.WriteLine(numeros[0]);
```
---
## 📌 Bucles
Los bucles permiten ejecutar un bloque de código repetidamente.

### **JavaScript**
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}

let j = 0;
while (j < 5) {
    console.log(j);
    j++;
}

let numeros = [1, 2, 3, 4, 5];
numeros.forEach(num => console.log(num));
```

### **Java**
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}

int j = 0;
while (j < 5) {
    System.out.println(j);
    j++;
}

int[] numeros = {1, 2, 3, 4, 5};
for (int num : numeros) {
    System.out.println(num);
}
```

### **C#**
```csharp
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}

int j = 0;
while (j < 5) {
    Console.WriteLine(j);
    j++;
}

int[] numeros = {1, 2, 3, 4, 5};
foreach (int num in numeros) {
    Console.WriteLine(num);
}
```

---
## 📌 Diferencias Clave
| Característica | JavaScript | Java | C# |
|--------------|------------|------|----|
| Tipado | Dinámico | Estático | Estático |
| Declaración de variables | `var`, `let`, `const` | `int`, `String`, `final` | `int`, `string`, `const` |
| Arreglos | Dinámicos (`push`, `pop`) | Tamaño fijo | Tamaño fijo (pero puede usar `List<T>`) |
| Bucles | `for`, `while`, `forEach` | `for`, `while`, `foreach` | `for`, `while`, `foreach` |

Este resumen muestra cómo JavaScript es más flexible, mientras que Java y C# requieren más estructura en la declaración de variables y arreglos. 🚀

