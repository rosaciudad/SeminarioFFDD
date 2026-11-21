# SeminarioFFDD

## Genómica y medicina de precisión en cáncer de mama

Este repositorio recoge el seminario de la asignatura **Fuentes de Datos Biomédicas y Web Semántica**  del Grado en Ingeniería de la Salud de la Universidad de Burgos.

## Descripción del proyecto

El cáncer de mama no es una única enfermedad: se divide en subtipos moleculares (clasificación PAM50: *Luminal A*, *Luminal B*, *HER2-enriquecido*, *Basal-like* y *Normal-like*) que tienen distinta agresividad y distinto tratamiento.

En este seminario integramos en R datos de tres fuentes públicas para estudiar la cohorte **TCGA-BRCA**.

**Pregunta de investigación:** ¿Cómo varían los marcadores de agresividad tumoral (inestabilidad genómica, carga mutacional e hipoxia) y los tratamientos entre los subtipos moleculares PAM50 del cáncer de mama, y qué influencia tienen las diferencias raciales y el contexto de obesidad?

## Fuentes de datos

| Fuente | Organismo | Qué datos usamos | Cómo se obtienen |
|---|---|---|---|
| [cBioPortal](https://www.cbioportal.org) | Memorial Sloan Kettering Cancer Center | Datos clínicos y moleculares del estudio `brca_tcga_pan_can_atlas_2018` (subtipo PAM50, FGA, TMB, hipoxia, supervivencia) | API, con el paquete `cbioportalR` |
| [NCI Genomic Data Commons (GDC)](https://portal.gdc.cancer.gov/projects/TCGA-BRCA) | National Cancer Institute (EE. UU.) | Datos demográficos, diagnósticos, tratamientos y seguimientos del proyecto TCGA-BRCA (formato JSON) | API, con el paquete `GenomicDataCommons` |
| [OMS – Global Health Observatory](https://www.who.int/data/gho) | Organización Mundial de la Salud | Prevalencia de obesidad en adultos, IMC ≥ 30 kg/m² (indicador `NCD_BMI_30A`) | Fichero CSV descargado de la web |

## Estructura del repositorio

```
SeminarioFFDD/
├── Analisis_Cancer_Mama.Rmd      # Documento principal: código y explicación
├── Analisis_Cancer_Mama.html     # Informe final generado con Knit
├── Analisis_Cancer_Mama          # Proyecto de RStudio
├── INPUT/
│   ├── DATA/
│   │   ├── clinical_tcga_brca.json   # Copia local de los datos del GDC (respaldo)
│   │   └── obesidad_oms.csv          # Datos de obesidad de la OMS
│   └── IMAGES/
│       └── fondo.jpg                 # Imagen de fondo del informe
├── .gitignore
└── README.md
```

## Cómo reproducir el análisis

1. Clonar o descargar el repositorio.
2. Abrir el proyecto en RStudio.
3. Instalar los paquetes necesarios: `tidyverse`, `jsonlite`, `tidyjson`, `cbioportalR` y `GenomicDataCommons` (este último desde Bioconductor con `BiocManager`).
4. Abrir `Analisis_Cancer_Mama.Rmd` y pulsar **Knit** para generar el informe HTML.

Si falla la conexión con las APIs, el documento incluye líneas comentadas para cargar los datos desde los ficheros de la carpeta `INPUT/DATA`.

## Autoras

- Rosa Isabel Ciudad García
- Maroua Zaroual Houbbi
- Maryam El Haouzi
