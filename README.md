El ciclo de vida DevOps es un enfoque que integra desarrollo (Dev) y operaciones (Ops) para entregar software de manera continua, rápida y confiable. Se basa en la automatización, la colaboración y la monitorización constante

Cómo aplicarlo en un proyecto real
Ejemplo: Supongamos que desarrollas una API en .NET Core para tu empresa.

Planificación: Historias en Azure Boards.
Desarrollo: Código en GitHub con PRs y revisiones.
CI/CD: Pipeline en Azure DevOps que:
    Compila el proyecto.
    Ejecuta tests unitarios.
    Genera imagen Docker.
Despliegue: Kubernetes en Azure AKS con Helm Charts.
Monitorización: Logs en ELK y métricas en Prometheus/Grafana.
Feedback: Revisar métricas de uso y errores para nuevas iteraciones.

Documentacion de proceso de subida, pull request y mergeo:
1. Subida de código desde local a GitHub (rama feature/nueva-funcionalidad)
Pre-requisitos

Tener Git instalado (git --version).
Repositorio remoto en GitHub.
Acceso con credenciales (HTTPS o SSH) y permisos de escritura.


A. Clonar el repositorio

En GitHub, copia la URL del repositorio:

HTTPS: https://github.com/<organizacion>/<repositorio>.git
SSH: git@github.com:<organizacion>/<repositorio>.git


En tu terminal:
Shellgit clone <URL-del-repositorio>Mostrar más líneas



B. Crear y cambiar a la rama de feature

Asegúrate de tener la última versión de main:
Shellgit checkout maingit pull origin mainMostrar más líneas

Crea la rama y cámbiate a ella:
Shellgit checkout -b feature/nueva-funcionalMostrar más líneas



C. Realiza cambios y haz commit

Añade los archivos modificados:
Shellgit add .Mostrar más líneas

Crea el commit:
Shellgit commit -m "feat: implementar nueva funcionalidadMostrar más líneas



D. Sube la rama al remoto
Shellgit push -u origin feature/nueva-funcionalMostrar más líneas

Crear Pull Request en GitHub (Interfaz Web)
A. Acceder a la sección de Pull Requests

Ve al repositorio en GitHub.
Haz clic en Pull requests → New pull request.


B. Configurar el PR

Selecciona:

Base branch: main
Compare branch: feature/nueva-funcionalidad


Haz clic en Create pull request.


C. Completar detalles

Título: feat: nueva funcionalidad X
Descripción (plantilla sugerida):
Markdown ## Resumen Implementa la funcionalidad X que permite Y. ## Cambios principales - Endpoint: POST /api/x - Validaciones: ... - DTOs: ... ## Pruebas - Unitarias: 28 tests pasando - Manuales: casos A, B, C ## Checklist - [x] Linter/format - [x] Tests unitarios - [x] Sonar/Quality Gate OKMostrar más líneas



Añadir comentarios y solicitar revisión

En la pestaña Conversation, añade comentarios generales.
En Files changed, comenta líneas específicas si es necesario.
Asigna revisores en el panel derecho (Reviewers).


Mergear el Pull Request

Espera aprobación y que los checks (CI/CD) estén en verde.
Haz clic en Merge pull request.
Elige estrategia:

Squash merge (recomendado para mantener historial limpio).


Confirma el merge.
(Opcional) Elimina la rama feature/nueva-funcionalidad en remoto.
