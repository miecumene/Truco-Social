# Truco-Social 3D

**Juego de Truco social 3D en Unity** — multijugador, interactivo y centrado en la experiencia social alrededor del Truco.

---

## 📘 Leer primero: GDD

El documento principal de diseño y referencia del juego se encuentra aquí:

[**docs/GDD.md**](docs/GDD.md)

> Este GDD es la fuente de verdad para todas las mecánicas, gestos, personalización, progresión y flujo de juego. Ideal para desarrolladores y para uso con herramientas de IA.

---

## 🏗️ Descripción del proyecto

- Proyecto: **Truco Social** — juego multijugador social basado en Truco argentino.
- Estado: **WIP**
- Enfoque:
  - Interacción social y faroleo entre jugadores.
  - Gestos y señales como mecánica de comunicación.
  - Personalización de avatares y cartas.
  - Progresión con experiencia, niveles y recompensas cosméticas.
  - Partidas rápidas en un entorno 3D estilizado, con cámara mínima y controles con mouse.
- Escenario inicial: habitación plana centrada en la mesa y los personajes; escenarios adicionales (bar, café, playa) previstos para futuras expansiones.

---

## 📂 Estructura del repositorio

truco-social/
├── docs/ # Documentación y diseño del juego (GDD, mecánicas, UI/UX, networking, gestos)
├── unity/TrucoSocial/ # Proyecto Unity (no incluir Library/, Temp/, Build/)
├── assets/ # Concept art y referencias visuales
├── README.md # Este archivo
└── LICENSE # Licencia del proyecto

---

> Nota: Las carpetas `docs` y `README.md` son la primera referencia para cualquier desarrollador o IA que trabaje sobre este proyecto.

---

## ⚙️ Requisitos

- Unity (versión indicada en `unity/TrucoSocial3D/ProjectSettings/ProjectVersion.txt`)
- Git
- Git LFS (recomendado para assets grandes)
- Conexión a internet para multijugador y sincronización de Cloud

---

## 🚀 Cómo empezar (local)

1. Clonar el repositorio:
```bash
git clone git@github.com:miecumene/Truco-Social.git
cd Truco-Social
