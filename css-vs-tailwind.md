# Guía de Introducción a Tailwind CSS

## Diferencia entre CSS Tradicional y Tailwind CSS

### 1. Estilos con CSS Tradicional
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <style>
        .btn {
            background-color: blue;
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <button class="btn">Haz clic aquí</button>
</body>
</html>
```

### 2. Estilos con Tailwind CSS
```html
<button class="bg-blue-500 text-white py-2 px-4 rounded">Haz clic aquí</button>
```

En Tailwind, en lugar de escribir reglas CSS en un archivo separado, usamos clases utilitarias directamente en los elementos HTML.

## Ejemplos Comparativos


| Característica            | CSS Tradicional                                | Tailwind CSS             |
| ------------------------- | ---------------------------------------------- | ------------------------ |
| Color de fondo            | `.bg-red { background-color: red; }`           | `class="bg-red-500"`     |
| Tamaño de texto           | `.text-lg { font-size: 18px; }`                | `class="text-lg"`        |
| Margen                    | `.mt-4 { margin-top: 16px; }`                  | `class="mt-4"`           |
| Padding                   | `.p-4 { padding: 16px; }`                      | `class="p-4"`            |
| Bordes redondeados        | `.rounded { border-radius: 5px; }`             | `class="rounded"`        |
| Ancho máximo              | `.max-w-md { max-width: 28rem; }`              | `class="max-w-md"`       |
| Altura                    | `.h-16 { height: 4rem; }`                      | `class="h-16"`           |
| Alineación de texto       | `.text-center { text-align: center; }`         | `class="text-center"`    |
| Flexbox                   | `.flex { display: flex; }`                     | `class="flex"`           |
| Justificación             | `.justify-center { justify-content: center; }` | `class="justify-center"` |
| Alineación de items       | `.items-center { align-items: center; }`       | `class="items-center"`   |
| Espaciado entre elementos | `.space-x-4 { margin-right: 16px; }`           | `class="space-x-4"`      |
| Opacidad                  | `.opacity-50 { opacity: 0.5; }`                | `class="opacity-50"`     |
