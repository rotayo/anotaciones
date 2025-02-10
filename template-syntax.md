## Sintaxis en Templates de Angular 18+

Los templates son el HTML de nuestro componente, la parte visibile e interactuable. Tiene su propia sintax para combinar HTML con TypeScript

---
### 🔹 Interpolación `{{ }}`

La interpolación `{{ }}` en Angular permite insertar valores dinámicos dentro del HTML de un componente, enlazando datos desde TypeScript al template de manera sencilla.

La sintaxis básica es:

```html
<p>Hola, {{ username }}!</p>
```

```typescript
username = 'Juan';
```

📌 **Salida en el navegador:**
```html
<p>Hola, Juan!</p>
```

---

### 🔹 **Expresiones en Interpolación**

También se pueden utilizar expresiones simples dentro de `{{ }}`:

```html
<p>La suma es: {{ 2 + 3 }}</p>
<p>Usuario: {{ getUser() }}</p>
```

```typescript
getUser() {
  return 'Carlos';
}
```

📌 **Salida:**
```html
<p>La suma es: 5</p>
<p>Usuario: Carlos</p>
```

⚠️ **Nota:** No se recomienda hacer cálculos complejos en la interpolación, ya que pueden afectar el rendimiento.

---

### 🔹 **Uso con Propiedades de Objetos**

```html
<p>Producto: {{ product.name }}</p>
<p>Precio: ${{ product.price }}</p>
```

```typescript
product = { name: 'Laptop', price: 1200 };
```

📌 **Salida:**
```html
<p>Producto: Laptop</p>
<p>Precio: $1200</p>
```

---

### 🔹 **Interpolación con Operadores Ternarios**

Se pueden usar operadores condicionales dentro de `{{ }}`:

```html
<p>{{ isAdmin ? 'Eres administrador' : 'Eres usuario' }}</p>
```

```typescript
isAdmin = true;
```

📌 **Salida:**
```html
<p>Eres administrador</p>
```

---

### **Resumen rápido**

| Característica | Uso |
|--------------|-----|
| **Mostrar valores dinámicos** | `{{ variable }}` |
| **Expresiones simples** | `{{ 10 + 20 }}` |
| **Llamar métodos** | `{{ getUser() }}` |
| **Acceder a propiedades** | `{{ objeto.propiedad }}` |
| **Condiciones ternarias** | `{{ isAdmin ? 'Sí' : 'No' }}` |


### 🔹 **@if (Directiva estructural)**

`@if` es una directiva estructural introducida en Angular 18+ que permite renderizar condicionalmente elementos en el template sin necesidad de `ngIf`. Se usa de la siguiente manera:

```html
@if (isLoggedIn) {
  <p>Bienvenido, usuario</p>
} @else {
  <p>Por favor, inicia sesión</p>
}
```

#### **Características:**
- Más limpio y fácil de leer en comparación con `*ngIf`.
- Soporta `@else` y `@elseif` directamente.
- Evita la necesidad de usar `<ng-template>` para manejar `else`.

#### **Ejemplo con `@elseif`:**
```html
@if (userRole === 'admin') {
  <p>Panel de administrador</p>
} @elseif (userRole === 'editor') {
  <p>Panel de edición</p>
} @else {
  <p>Acceso restringido</p>
}
```

---

### 🔹 **@for (Directiva estructural)**

`@for` reemplaza a `*ngFor` y se usa para iterar sobre listas en los templates de Angular.

#### **Ejemplo de uso:**
```html
@for (product of products; track product.id) {
  <div>{{ product.name }}</div>
}
```

#### **Características:**
- `track product.id`: Optimiza el rendimiento usando el identificador único del elemento, si no tenemos un id como en el caso de ese objeto podemos usar `track $index`.
- Evita el uso de `*ngFor`, haciendo el código más limpio y con mejor rendimiento.
- Se pueden definir variables locales dentro del bucle:

```html
@for ((product, index) of products) {
  <p>{{ index + 1 }}. {{ product.name }}</p>
}
```

---

### 🔹 **Paréntesis `()` (Binding de eventos)**

Los paréntesis `()` se usan para **enlazar eventos** de elementos del DOM con métodos en el componente TypeScript.

#### **Ejemplo:**
```html
<button (click)="sayHello()">Haz clic</button>
```

```typescript
sayHello() {
  alert('Hola mundo');
}
```

#### **Ejemplos de eventos comunes:**
- `(click)`: Detecta clics.
- `(input)`: Captura cambios en un `<input>`.
- `(keydown)`: Detecta teclas presionadas.

```html
<input (input)="onInput($event)" />
```

```typescript
onInput(event: Event) {
  console.log((event.target as HTMLInputElement).value);
}
```

---

### 🔹 **Corchetes `[]` (Property Binding)**

Los corchetes `[]` se usan para **enlazar propiedades** de elementos HTML con valores del componente.

#### **Ejemplo:**
```html
<img [src]="imageUrl" />
```

```typescript
imageUrl = 'https://example.com/image.jpg';
```

#### **Ejemplo con clases y atributos dinámicos:**
```html
<div [class.active]="isActive"></div>
<input [disabled]="isDisabled" />
```

---

### **Resumen rápido**

| Sintaxis | Uso |
|----------|----|
| `@if (condición) {}` | Renderizado condicional en el template. |
| `@for (item of lista; track item.id) {}` | Iterar sobre listas sin usar `*ngFor`. |
| `()` | Binding de eventos (`(click)`, `(input)`, etc.). |
| `[]` | Property Binding (`[src]`, `[class]`, `[disabled]`, etc.). |
