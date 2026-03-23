# Aprende Machine Learning by BelloDev
![Imagen de logo de este repositorio](logo.png)

Este proyecto contiene un resumen de los principales conceptos y funciones de Machine Learning, organizado en dos grandes áreas: aprendizaje supervisado y no supervisado.

## Estructura del Proyecto
  1. Carpeta: Supervised:
  - Un archivo con el resumen de las funciones más importantes de Machine Learning supervisado.
  - Ejercicios de ejemplo para cada una de estas funciones, acompañados de sus métricas e interpretaciones.

  2. Carpeta: non_supervised:
  - Un archivo con el resumen de las funciones principales de Machine Learning no supervisado.
  - Ejemplos prácticos con sus respectivas métricas.

Este repositorio está pensado como un recurso de consulta y práctica para quienes desean comprender y aplicar técnicas de Machine Learning tanto supervisadas como no supervisadas, con ejemplos claros y explicaciones de las métricas utilizadas.


## Instalación 

### 1. Clonar el repositorio
Abre CMD o PowerShell o bash y ejecuta (reemplaza la URL por la de tu repositorio cuando la tengas):

```powershell cmd bash
git clone https://github.com/usuario/ruta-del-repositorio.git
cd ruta-del-repositorio
```

### 2. Crear y activar el entorno virtual con UV

Ejecuta el siguiente comando:
```
uv venv
```
Al ejecutar este comando, UV creará y activará automáticamente un entorno virtual, instalará la versión de Python especificada en el proyecto y todas las dependencias definidas en `pyproject.toml`. ¡Todo el proceso es automático gracias a UV!

> **Nota:** Si no tienes UV instalado, este comando dará error. Dirígete al apartado 3 para ver qué es UV y cómo instalarlo.

Para activar el entorno virtual manualmente:

En CMD:
```cmd
.venv\Scripts\activate
```
En PowerShell:
```powershell
.venv\Scripts\Activate.ps1
```

En bash:
```bash
source .venv/bin/activate
```

#### Usar el entorno virtual como predeterminado en VSCode
Para que VSCode use este entorno virtual automáticamente:
1. Abre la paleta de comandos (`Ctrl+Shift+P`).
2. Escribe y selecciona: `Python: Seleccionar intérprete`.
3. Elige el intérprete que aparece en `.venv` dentro de tu proyecto.

---

### 3. ¿Qué es UV y cómo se instala?

UV es una herramienta ultrarrápida para la gestión de entornos y dependencias en proyectos Python. Permite crear entornos virtuales, instalar la versión de Python requerida y todas las dependencias de forma automática y eficiente.

Para instalar UV, ejecuta en tu terminal:
```bash
pip install uv
```
Puedes encontrar más información en el repositorio oficial: https://github.com/astral-sh/uv

---

Hecho con excelencia por BelloDev
