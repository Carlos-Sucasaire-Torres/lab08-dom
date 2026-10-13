# Tarea: Mi componente interactivo

## Componente elegido
Gestor de Tareas (To-Do List) interactivo para agregar, tachar y eliminar pendientes.

## Version 1: solo DOM
const listaTareas = document.querySelector("#listaTareas");
const li = document.createElement("li");
li.textContent = "Tarea de prueba";
listaTareas.appendChild(li);

## Version 2: con eventos
formTarea.addEventListener("submit", (e) => {
    e.preventDefault();
    if (inputTarea.value.trim() === "") {
        mensajeError.style.display = "block";
    }
});

## Version 3: con clases y objetos
class Tarea {
    constructor(titulo) {
        this.titulo = titulo;
        this.completada = false;
    }
    completar() {
        this.completada = !this.completada;
    }
    obtenerEstado() {
        return this.completada ? "Completada" : "Pendiente";
    }
}

## Donde uso DOM, eventos y objetos

| Parte | Descripción en el Código |
| --- | --- |
| **DOM** | `querySelector`, `createElement`, `appendChild`, `classList`. |
| **Eventos** | `submit` en formulario, `input` en campo de texto y `click` en botones. |
| **Objetos** | Clase `Tarea` (`new Tarea(titulo)`) y array `misTareas`. |

## Pruebas realizadas

| Acción | Resultado esperado | Resultado obtenido | Cumple (Sí / No) |
| --- | --- | --- | --- |
| Agregar tarea vacía | Muestra mensaje de error rojo | Muestra error sin usar alert | Sí |
| Escribir en input con error | Oculta mensaje de error | Ocultó el mensaje | Sí |
| Agregar "Estudiar" | Agrega elemento a la lista | Agregó tarea a la lista | Sí |
| Clic en texto de tarea | Tacha la tarea | Tarea tachada | Sí |
| Clic en "Eliminar" | Elimina la tarea | Tarea eliminada | Sí |

## Por que me sirvio disenar asi mi clase
Permite encapsular el estado (`titulo` y `completada`) y sus métodos (`completar`) sin saturar el código global.