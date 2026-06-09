# Carpeta de entrega

Esta carpeta contiene la version reproducible de la solucion computacional para la Solemne 2 de Optimizacion. El archivo principal es el notebook `GA_Ruteo_Scheduling_Camiones.ipynb`, que desarrolla el problema de ruteo y scheduling de camiones cisterna usando un Algoritmo Genetico.

## Archivos

| Archivo | Descripcion |
|---|---|
| `GA_Ruteo_Scheduling_Camiones.ipynb` | Notebook principal con teoria aplicada, implementacion, validacion y graficos. |
| `requirements.txt` | Dependencias necesarias para ejecutar el notebook. |
| `instalar_dependencias.ps1` | Script de instalacion para PowerShell y registro del kernel de Jupyter. |
| `figuras_ga/` | Carpeta con graficos generados por el notebook. |

## Ejecucion

Desde la raiz del repositorio:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\entrega\instalar_dependencias.ps1
```

Despues de instalar, abrir el notebook y seleccionar el kernel:

```text
Python (Opti GA)
```

Tambien se puede instalar de forma manual:

```powershell
python -m pip install -r .\entrega\requirements.txt
python -m ipykernel install --user --name opti-ga --display-name "Python (Opti GA)"
```

## Contenido tecnico del notebook

El notebook esta organizado para que pueda leerse como base del informe:

- Definicion del problema y datos de entrada.
- Creacion de entidades: camiones, estaciones, demandas y cromosomas.
- Representacion de soluciones mediante rutas, cortes y asignaciones de compartimentos.
- Evaluacion de factibilidad y costo.
- Implementacion del Algoritmo Genetico.
- Validacion de la solucion final.
- Scheduling de carga en deposito.
- Generacion de graficos para analisis.

## Solucion registrada

| Camion | Ruta | C0 | C1 | Carga C0 | Carga C1 |
|---|---|---|---|---:|---:|
| T1 | Deposito -> 1 -> 2 -> 4 -> Deposito | Regular | Diesel | 8000 L | 6000 L |
| T2 | Deposito -> 3 -> Deposito | Diesel | Regular | 3000 L | 2500 L |

| Indicador | Valor |
|---|---:|
| Distancia total | 115 km |
| Costo por distancia | 230 |
| Costos fijos | 900 |
| Shortage | 0 |
| Costo total | 1130 |

## Graficos

Los graficos disponibles en `figuras_ga/` son:

- `01_gantt_carga.png`
- `02_rutas_solucion_ga_1130.png`
- `03_fill_ratios_solucion_ga_1130.png`
- `04_costos_solucion_ga_1130.png`
- `05_demanda_escenarios.png`
- `06_convergencia_ga_1130.png`

Estos archivos se pueden regenerar ejecutando completamente el notebook.
