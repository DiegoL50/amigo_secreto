# Amigo Selector App

Este proyecto tiene como objetivo fortalecer tus habilidades en lógica de programación mediante la implementación de una aplicación interactiva que permite gestionar una lista de amigos y seleccionar un amigo al azar.

## Características

1. **Agregar Amigos**  
   Permite a los usuarios agregar nombres a una lista, verificando que el campo no esté vacío antes de añadirlo.

2. **Mostrar Lista de Amigos**  
   Los amigos agregados se muestran dinámicamente en una lista en la interfaz.

3. **Sortear un Amigo**  
   Selecciona un amigo al azar de la lista. Si la lista está vacía, se muestra un mensaje de alerta.

## Requisitos Previos

- Conocimientos básicos de HTML, CSS y JavaScript.
- Un navegador web para ejecutar la aplicación.
- Un editor de texto (como Visual Studio Code) para explorar el código fuente.

## Estructura del Proyecto

- **HTML**  
  Contiene la estructura principal de la aplicación con campos de entrada, botones y áreas para mostrar resultados.

- **CSS**  
  Para el estilo visual (puedes personalizarlo según tus necesidades).

- **JavaScript**  
  Contiene toda la lógica de la aplicación en funciones para agregar amigos, mostrar la lista y realizar el sorteo.

## Código Principal

```javascript
let amigos = [];

function agregarAmigo() {
  let nombreAmigo = document.getElementById("amigo").value;

  if (nombreAmigo.trim() === "") {
    alert("Por favor, inserte un nombre");
  } else {
    amigos.push(nombreAmigo);
    document.querySelector("#amigo").value = "";
    mostrarListaAmigo();
  }
}

function mostrarListaAmigo() {
  let listaAmigos = document.querySelector("#listaAmigos");
  listaAmigos.innerHTML = "";

  for (let index = 0; index < amigos.length; index++) {
    const element = amigos[index];

    let listaHTML = document.createElement("li");
    listaHTML.textContent = element;
    listaAmigos.appendChild(listaHTML);
  }
}

function sortearAmigo() {
  let cantidadAmigos = amigos.length;
  if (cantidadAmigos === 0) {
    alert("Por favor, inserte un nombre antes de sortear");
  } else {
    let indiceAmigo = Math.floor(Math.random() * cantidadAmigos);
    let resultadoHTML = document.querySelector("#resultado");
    resultadoHTML.innerHTML = amigos[indiceAmigo];
  }
}
