# Proyecto-final-posix
# 🎬 Sistema de Ventas de Boletos de Cine - MiniPipeline POSIX

## 📌 Descripción
Sistema automatizado para procesar datos de ventas de boletos de cine, generando reportes para visualización en dashboard web.

## 🚀 Características Principales
- ✅ Procesamiento ETL con scripts Bash
- ✅ Base de datos SQLite para almacenamiento
- ✅ Generación automática de reportes (JSON/CSV)
- ✅ Integración con dashboards web

## 📂 Estructura del Proyecto

```text
📦 ventas_cine_posix
├── 📂 raw_data          # Datos brutos en CSV
│   └── 📄 ventas.csv
├── 📂 scripts
│   ├── 🐚 etl.sh         # Script de transformación
│   └── 🐚 reportes.sh    # Generador de reportes
├── 📂 db
│   └── 🗃️ cine.db        # Base de datos SQLite
└── 📂 exports           # Reportes para dashboard
`````
## 🔧 Requisitos
- Bash (Linux/MacOS/Windows)
- sqlite3
- awk, sed, grep

## 🚀 Uso

- ./scripts/etl.sh

- ./scripts/reportes.sh



![grafica](https://github.com/user-attachments/assets/828815bb-3d40-4f47-bb04-17401ba7ec97)


## 📝 Reportes Generados
- Ventas por película

- Boletos vendidos por horario

- Ingresos por tipo de sala

## 📌 Ejemplo de Datos

Fecha , Pelicula , Sala , Boletos , Total


2025-04-01,Avengers,Sala1,45,6750.00
