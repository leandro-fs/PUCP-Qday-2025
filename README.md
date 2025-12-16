# PUCP-Qday-2025

## PUCP Quantum Day 2025

### Hands On: tour por la consola Qiskit

**Instructores:**
- Ing. Leandro Batlle
- Ing. Marcos Frankiensztajn

**Institución:** Fundación Sadosky

---

## Resumen del Taller

Este taller práctico ofrece una introducción completa al desarrollo de programas cuánticos usando Qiskit, el SDK de IBM para computación cuántica. El enfoque está en proporcionar una experiencia hands-on que permita a los participantes comenzar a programar circuitos cuánticos desde cero.

### Temario Principal

1. **Introducción a la Fundación Sadosky**
   - Contexto institucional del taller

2. **Computación Cuántica: Simulación vs Hardware Físico**
   - Diferencias entre simuladores locales y QPUs reales
   - Recursos y limitaciones de cada enfoque
   - Referencia: [quantumspain-project.es](https://quantumspain-project.es)

3. **Python SDK para Computación Cuántica**
   - Qiskit como herramienta principal
   - Estructura de paquetes y módulos

4. **Entornos Jupyter: Local vs Nube**
   - Comparación de ventajas y desventajas
   - Configuración de ambientes de desarrollo

5. **Hello (Q)World!**
   - Primer programa cuántico
   - Circuito de Bell y mediciones

---

## Recursos y Enlaces Importantes

### Documentación Oficial
- **Panel de control IBM Quantum:** https://quantum.cloud.ibm.com
- **Guía de instalación:** https://quantum.cloud.ibm.com/docs/es/guides/install-qiskit
- **Tutorial Hello World:** https://quantum.cloud.ibm.com/docs/es/tutorials/hello-world
- **Quick Start:** https://quantum.cloud.ibm.com/docs/es/guides/quick-start
- **IBM Quantum Learning (español):** https://quantum.cloud.ibm.com/learning/es

### Repositorio del Taller
```bash
git clone https://github.com/leandro-fs/PUCP-Qday-2025.git
```

---

## Entornos de Desarrollo

### Comparación: Entorno Jupyter

| Entorno | Ventajas | Desventajas | Comentarios |
|---------|----------|-------------|-------------|
| **Local** | - Control de versiones<br>- Independencia de conectividad | - Recursos limitados<br>- Configuración inicial | Evitar usar el entorno del SO directamente |
| **Nube** | - Sin instalación local<br>- Acceso inmediato | - Costo potencial<br>- Dependencia de conectividad | No incluye tiempo de runtime en plan gratuito |

### Jupyter Notebooks
- **Prueba online:** https://jupyter.org/try-jupyter/lab/
- **Características:**
  - Celdas Markdown y ejecutables
  - Múltiples kernels: Python, C++, R, SQLite, Octave
  - Archivos JSON que incluyen código, markdown y resultados
  - Arquitectura: muchos notebooks → un kernel
  - Python: soporte para introspección y debugging

---

## Instalación y Configuración

### Distribuciones de Python: Comparación

#### Python.org (CPython Oficial) vs Anaconda

**Características Generales:**

| Aspecto | CPython Oficial | Anaconda |
|---------|----------------|----------|
| **Mantenedor** | Python Software Foundation | Anaconda Inc. (comercial) |
| **Licencia** | PSF (FLOSS) | BSD (gratuito) + Comercial |
| **Tamaño** | ~25-50 MB | ~3-5 GB (instalación completa) |
| **Gestor de paquetes** | pip | conda (+ pip) |
| **Repositorio** | PyPI (~500k paquetes) | Anaconda (~8k paquetes) |
| **Público objetivo** | Propósito general | Ciencia de datos / ML |

**Funcionalidades:**

| Aspecto | CPython Oficial | Anaconda |
|---------|----------------|----------|
| **Bibliotecas preinstaladas** | Solo librería estándar | NumPy, pandas, Jupyter, +250 paquetes |
| **Manejo de binarios** | Fuente + wheels | Binarios precompilados |
| **Entornos virtuales** | venv (stdlib) | Entornos conda |
| **Multi-lenguaje** | Solo Python | Python, R, Julia, etc. |
| **Integración sistema** | Nivel SO | Autocontenido |

**Rendimiento:**

| Aspecto | CPython Oficial | Anaconda |
|---------|----------------|----------|
| **Resolución de dependencias** | Básica (pip) | Avanzada (múltiples solvers) |
| **Velocidad de instalación** | Rápida (pip) | Más lenta (conda)<br>Más rápida (mamba) |
| **Espacio en disco** | Mínimo | Considerable |
| **Filosofía** | FLOSS puro | Mixta (algunos comerciales) |

### Instalación en Windows
- Guía completa: https://www.datacamp.com/es/tutorial/installing-anaconda-windows

### Instalación en Linux/MacOS

1. **Instalar Conda**
   - Descargar desde: https://www.anaconda.com
   - Nota: Requiere registración

2. **Crear entorno `Qday25`:**
   ```bash
   git clone https://github.com/leandro-fs/PUCP-Qday-2025.git
   cd PUCP-Qday-2025
   conda env create --solver libmamba --file Qday25.yml --name Qday25
   conda init  # Solo una vez durante la instalación
   conda activate Qday25  # En cada sesión
   ```
   ⚠️ **Nota:** El flag `--solver` acepta `{classic, libmamba}`

3. **Ejecutar Jupyter Lab:**
   ```bash
   cd  # Ir a la carpeta del proyecto
   conda activate Qday25  # Nuevo prompt: ➜ Qday25 git:(main) ✗
   jupyter lab  # Abre el navegador automáticamente
   ```

### Actualización del Entorno

**Opción 1 - Desde archivo:**
```bash
cd  # Ir a la carpeta del proyecto
conda activate Qday25
conda env update --file Qday25.yml
```
📖 Documentación: https://docs.conda.io/projects/conda/en/stable/commands/env/update.html

**Opción 2 - Actualización general:**
```bash
conda activate Qday25
conda update --all
```
📖 Documentación: https://docs.conda.io/projects/conda/en/stable/commands/update.html

---

## Configuración de IBM Quantum Platform

### Credenciales y API Key

**Importante:** Distinguir entre dos tipos de credenciales:

- ❌ **API keys de IBM Cloud** (https://cloud.ibm.com/iam/apikeys)
  - Para gestión de recursos de infraestructura
  
- ✅ **API token de IBM Quantum Platform** (https://quantum.ibm.com/)
  - Para computación cuántica (¡este es el que necesitás!)

### Pasos para obtener el API Token

1. Ir a: https://quantum.ibm.com/ (NO a cloud.ibm.com)
2. Iniciar sesión o crear cuenta
3. Seleccionar "Configuración de cuenta" / "Account settings"
4. En la sección "API token", copiar el token (cadena larga de caracteres)

**Referencia:** https://quantum.cloud.ibm.com/docs/es/guides/save-credentials

### Plan Gratuito (Open Plan)

> "Get 10 free minutes of runtime each month with an Open Plan instance, which is required to run and manage workloads on your account"

El plan gratuito incluye:
- 10 minutos de tiempo de ejecución mensual en QPUs reales
- Acceso a simuladores sin restricción
- Acceso a la plataforma de aprendizaje

**Notebook de referencia:** `credenciales.ipynb` (incluido en el repositorio)

---

## Conclusiones Principales

1. **La Computación Cuántica es en la nube**
   - Los QPUs reales están accesibles remotamente
   - Simuladores pueden ejecutarse localmente

2. **La Programación es local**
   - Desarrollo de código en ambiente propio
   - Control de versiones y flujo de trabajo habitual

3. **Python es el lenguaje dominante**
   - Qiskit como SDK principal
   - Ecosistema maduro de herramientas

4. **quantum.cloud.ibm.com es un mundo por descubrir**
   - Documentación extensa en español
   - Tutoriales interactivos
   - Acceso a hardware real

### Resumen de Entornos Python

| Entorno | Ventajas | Desventajas |
|---------|----------|-------------|
| **Local (python.org)** | - Control de versiones | - Recursos limitados<br>- Configuración manual |
| **Local (Anaconda)** | - Control de versiones<br>- Entorno replicable<br>- Binarios precompilados | - Recursos limitados<br>- Mayor tamaño |
| **Nube** | - Sin instalación<br>- Acceso inmediato | - Costos potenciales<br>- Colaboración limitada |

---

## Materiales del Taller

Este repositorio incluye:
- 📓 Notebooks de Jupyter con ejemplos prácticos
- 🔧 Archivo `Qday25.yml` para configuración de entorno
- 📚 Guías de referencia rápida
- 💻 Código fuente de ejemplos Hello World

---

**¿Preguntas?**

Para consultas adicionales, referirse a:
- Documentación oficial de Qiskit
- Foros de IBM Quantum Platform
- Comunidad de usuarios en GitHub
