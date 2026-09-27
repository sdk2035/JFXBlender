# JFXBlender 🎨🚀

JFXBlender es un entorno de modelado 3D, animación y simulación cinemática inspirado en la arquitectura conceptual de Blender, reimplementado y optimizado para ejecutarse de forma nativa sobre la plataforma de alto rendimiento GraalVM y el marco gráfico JavaFX 3D.

Diseñado como el motor visualizador y modelador de referencia para la suite de ingeniería y robótica (jfx-*), JFXBlender sustituye la arquitectura de CPython tradicional por el marco políglota Truffle. Esto permite ejecutar scripts de automatización 3D, cálculos cinemáticos y sombreadores gráficos en tiempo real con compilación JIT (Just-In-Time) sin el sobrecosto de la copia de datos en memoria.

## 🌟 Características Principales

- **Entorno 3D Políglota sobre GraalVM:** Generación y manipulación de mallas (meshes), curvas, materiales y esqueletos de animación mediante un núcleo basado en Java 21+.
- **Motor de Renderizado JavaFX 3D / Vulkan:** Pipeline gráfico de alto rendimiento capaz de integrar interfaces de usuario interactivas con viewports tridimensionales acelerados por hardware.
- **Soporte para Add-ons Políglotas:** Ejecución directa de scripts y extensiones en Python (GraalPy), RascalMPL y JavaScript a través del runtime Truffle, eliminando las limitaciones del GIL (Global Interpreter Lock).
- **Simulación Robótica y Mecatrónica:** Conectividad nativa con modelos cinemáticos de exoesqueletos, brazos industriales y dinámicas físicas del ecosistema jfx-*

## 🏗️ Arquitectura del Sistema

```
+-------------------------------------------------------------------------+
|                  JFXBlender UI & Viewport 3D (JavaFX)                   |
+-------------------------------------------------------------------------+
|                    GraalVM Truffle Polyglot Engine                      |
|  +--------------------+  +--------------------+  +-------------------+  |
|  | GraalPy (Add-ons)  |  | Modelica Kinematics|  | Rascal DSL ASTs   |  |
|  +--------------------+  +--------------------+  +-------------------+  |
+-------------------------------------------------------------------------+
|           GraalVM Native Image / Substrate VM (Zero-Copy JIT)           |
+-------------------------------------------------------------------------+
```

## 🚦 Inicio Rápido
### Prerrequisitos

- GraalVM JDK 21+
- Componente graalpy habilitado en la instalación de GraalVM.

### Compilación y Ejecución
**Bash**
```bash
# Clonar el repositorio
git clone https://github.com/jfx-suite/JFXBlender.git
cd JFXBlender

# Compilar el proyecto con Gradle
./gradlew build

# Generar el ejecutable nativo ultrarrápido
./gradlew nativeCompile```
