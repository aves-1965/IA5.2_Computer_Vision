# 📘 Guía de Supervivencia: Entornos de IA en Linux

**Proyecto:** `IA5.2_Computer_Vision`

**Versión de Python recomendada:** 3.11

---

## 1. Preparación del Espacio (Git)

Para evitar lentitud en VS Code y conflictos con otros archivos:

* **Acción:** Clonar el repositorio en una carpeta limpia (ej. `~/Documentos/GitHub/`).
* **Por qué:** Si clonas dentro de una carpeta con miles de archivos (como `/TUIA`), Git intentará indexar todo, consumiendo RAM y procesador innecesariamente.

## 2. Creación del Entorno Aislado (`venv`)

El entorno virtual es una "caja" donde viven las librerías de este proyecto sin molestar al resto del sistema.

**Bash**

```
# 1. Crear la caja usando Python 3.11 (el estable)
python3.11 -m venv venv-ia

# 2. Entrar a la caja (Activar)
source venv-ia/bin/activate
```

> **Nota:** Sabrás que estás dentro porque verás `(venv-ia)` al inicio de tu terminal.

## 3. Instalación de Dependencias

Usamos un archivo `requirements.txt` para automatizar la "lista de compras".

**Bash**

```
# Instalar todo lo necesario + el puente para Jupyter (ipykernel)
pip install -r requirements.txt ipykernel
```

* **requirements.txt:** Contiene `torch`, `torchvision`, `numpy`, `matplotlib` y `Pillow`.
* **ipykernel:** Es el motor que permite que el archivo `.ipynb` hable con las librerías instaladas.

## 4. Vinculación en VS Code

Para que el archivo `.ipynb` use la "caja" que creamos:

1. Abrir el archivo `.ipynb`.
2. Click en **"Select Kernel"** (arriba a la derecha).
3. Elegir  **"Python Environments..."** .
4. Seleccionar  **`Python 3.11.x (venv-ia)`** .

---

## 🆘 Resolución de Problemas (Borrón y Cuenta Nueva)

Si el entorno se rompe o `pip` deja de funcionar, lo más sano es recrearlo:

**Bash**

```
rm -rf venv-ia                 # Borra la caja rota
python3.11 -m venv venv-ia     # Crea una nueva
source venv-ia/bin/activate    # Activa
pip install -r requirements.txt ipykernel # Reinstala todo
```
