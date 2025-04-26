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

# 📔 Bitácora Técnica: Desarrollo del Pipeline de Procesamiento de Datos

## 🗓️ Semana 1: Configuración Inicial del Entorno
### ✅ Objetivo Cumplido: 
Establecer la estructura base del pipeline.

### 🔧 Acciones Realizadas:
```bash
# Creación de estructura de directorios
mkdir -p minipipeline_equipoX/{raw_data,scripts,db,exports}

# Configuración inicial de la base de datos SQLite
sqlite3 db/base_de_datos.sqlite "CREATE TABLE usuarios (...); ..."
```
### ⚠️ Problemas y Soluciones:
## ⚠️ Problema

Error: unable to open database file	


## 🧐Causa

Permisos incorrectos en /db	



## ✅Solución

chmod 755 db/

### 🗓️ Semana 2: Desarrollo del Script ETL (etl.sh)
## ✅ Objetivo Cumplido:
Implementar el proceso completo de ETL.

## 🔄 Flujo Implementado:

### Extracción:

## bash
```bash
[ -s "raw_data/ventas.csv" ] || exit 1
```
### Transformación:

## awk
```bash
{gsub(/"/, ""); $2 = tolower($2)}
```
### Carga:

## sql
```bash
BEGIN TRANSACTION;
INSERT INTO ventas VALUES(...);
COMMIT;
```

### ⚠️ Problemas
## Error	                   
- Campos vacíos	            
- Fechas inválidas	          
## Solución
```bash
- awk 'NF < 5 {exit 1}'
- date -d "$fecha" "+%Y-%m-%d"
```


### 🗓️ Semana 3: Reportes Automatizados
## 📊 Consultas SQL

## sql
```bash
-- Top películas
SELECT pelicula, SUM(boletos) 
FROM ventas 
GROUP BY pelicula;
```


### 🚀 Generación de Reportes
## bash
```bash
sqlite3 -json db/cine.db "SELECT..." | jq > exports/reporte.json
```

### 📌 Lecciones Aprendidas
## 🔍 Validar datos desde el inicio

## ⚡ Usar transacciones SQL

## 🛠️ Dominar herramientas CLI (awk, jq)

### 📊 Métricas Finales
## Concepto	Valor
## ⏳ Tiempo	18 hrs
## 🐞 Errores	12
## 🔄 Versiones	15


