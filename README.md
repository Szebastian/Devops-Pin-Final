# Proyecto Integrador Final - PIN

## Integrantes del Grupo 21:
- Sebastián Contreras
- Tomás Santiago Moreno Juárez

---

## Índice:
1. [Introducción](#introducción)
2. [Diagrama de Arquitectura](#diagrama-de-arquitectura)
3. [Herramientas Utilizadas](#herramientas-utilizadas)
4. [Proceso de Implementación](#proceso-de-implementación)
   - Paso a paso para configurar el entorno y las herramientas
5. [Monitoreo y Visualización](#monitoreo-y-visualización)
   - Configuración de Prometheus y Grafana
6. [Links y Repositorios](#links-y-repositorios)
7. [Resolución de Problemas](#resolución-de-problemas)
   - Soluciones a los problemas encontrados
8. [Referencias](#referencias)
   - Documentación y enlaces útiles

---

## Introducción

Este proyecto tiene como objetivo integrar una solución DevOps utilizando herramientas modernas como Kubernetes, Docker, Jenkins, Prometheus y Grafana, con el propósito de implementar un sistema de monitoreo para aplicaciones y servicios desplegados en un clúster Kubernetes. 

La solución fue diseñada para proporcionar una infraestructura automatizada que permite la recolección y visualización en tiempo real de métricas de los servicios del clúster. El proyecto hace énfasis en la monitorización continua, utilizando herramientas de recolección de datos y su visualización en dashboards interactivos para facilitar la gestión y análisis de la infraestructura.

---

## Diagrama de Arquitectura

La arquitectura del proyecto está compuesta por las siguientes herramientas clave:

- **Minikube**: Clúster Kubernetes local para pruebas y desarrollo.
- **Docker**: Plataforma de contenedores utilizada para crear y gestionar aplicaciones dentro del clúster.
- **Jenkins**: Herramienta de integración continua y entrega continua (CI/CD), responsable de automatizar los pipelines de despliegue.
- **Prometheus**: Sistema de monitoreo de métricas en tiempo real, encargado de recolectar datos sobre los servicios y nodos del clúster.
- **Grafana**: Plataforma de visualización de métricas que se conecta a Prometheus para generar dashboards interactivos.

El diagrama de arquitectura ilustra cómo estas herramientas interactúan para ofrecer una solución eficiente, escalable y automatizada.

---

## Herramientas Utilizadas

- **Minikube**: Utilizado para crear un clúster Kubernetes local, lo que facilita el desarrollo y la ejecución de pruebas en un entorno controlado.
- **Docker**: Herramienta fundamental para la creación de contenedores de aplicaciones, lo que permite la portabilidad y escalabilidad de los servicios.
- **Jenkins**: Usado para gestionar los pipelines de integración y entrega continua, automatizando tareas de despliegue y monitoreo.
- **GitHub**: Repositorio que aloja el código fuente y las definiciones de los pipelines.
- **Prometheus**: Herramienta de monitoreo encargada de recolectar métricas de los servicios y nodos del clúster en tiempo real.
- **Grafana**: Plataforma de visualización que permite crear dashboards interactivos para analizar las métricas recolectadas por Prometheus.

---

## Proceso de Implementación

### 1. **Configuración del Clúster Local**
Se configuró un clúster de Kubernetes local utilizando Minikube. Esto permitió trabajar en un entorno aislado y seguro, ideal para desarrollo y pruebas. Además, se configuró la IP del clúster para la correcta resolución del dominio `front-pinfinal.com`.

### 2. **Configuración de Jenkins**
Jenkins fue instalado y configurado para interactuar con Kubernetes y Docker. Los pasos clave fueron:

- Instalación de los plugins necesarios para la integración con Docker y Kubernetes.
- Conexión con el repositorio de GitHub para obtener las definiciones de los pipelines y el código fuente de las aplicaciones.

### 3. **Ejecución de Pipelines**
Se automatizaron los siguientes pipelines con Jenkins:

- **deploy-nginx-exporter-cluster-pin-final-mundose**: Despliegue de un contenedor **NGINX Exporter** para la recolección de métricas relacionadas con NGINX.
- **prometheus-cluster-monitoreo-pin-final-mundose**: Despliegue de **Prometheus** y **Node Exporter** en el clúster para la recolección de métricas de servicios y nodos.
- **grafana-cluster-monitoreo-pin-final-mundose**: Despliegue de **Grafana** y configuración de la conexión con **Prometheus** para la visualización de métricas.

---

## Monitoreo y Visualización

**Prometheus** fue configurado para recolectar métricas en tiempo real desde los servicios y nodos dentro del clúster. La interfaz de **Prometheus** está disponible en:

- **Prometheus**: [http://front-pinfinal.com/services/prometheus](http://front-pinfinal.com/services/prometheus)

**Grafana** fue configurado para crear dashboards interactivos que visualizan las métricas de **Prometheus**. Esto permite un análisis detallado de la infraestructura y servicios del clúster. La interfaz de **Grafana** está disponible en:

- **Grafana**: [http://szebastian001/front-pinfinal/services/grafana](http://szebastian001/front-pinfinal/services/grafana)

---

## Links y Repositorios

- **Repositorio del Proyecto**: [GitHub - DevOps Pin Final](https://github.com/Szebastian/Devops-Pin-Final)
- **URL de Grafana**: [http://szebastian001/front-pinfinal/services/grafana](http://szebastian001/front-pinfinal/services/grafana)
- **URL de Prometheus**: [http://front-pinfinal.com/services/prometheus](http://front-pinfinal.com/services/prometheus)

---

## Resolución de Problemas

Durante la implementación del proyecto, se presentaron varios problemas que fueron solucionados con los siguientes enfoques:

- **Problema de Conexión entre Jenkins y Kubernetes**: La configuración de **kubeconfig** fue ajustada para asegurar que Jenkins pudiera acceder correctamente al clúster de Minikube.
  
- **Problema de Conexión entre Grafana y Prometheus**: Inicialmente, Grafana no podía conectarse a Prometheus debido a configuraciones erróneas de URL y credenciales. Este problema fue resuelto revisando y ajustando las configuraciones en ambos servicios.

---

## Referencias

- **Documentación de Docker**: [https://docs.docker.com/](https://docs.docker.com/)
- **Documentación de Kubernetes**: [https://kubernetes.io/docs/](https://kubernetes.io/docs/)
- **Documentación de Jenkins**: [https://www.jenkins.io/doc/](https://www.jenkins.io/doc/)
- **Documentación de Prometheus**: [https://prometheus.io/docs/](https://prometheus.io/docs/)
- **Documentación de Grafana**: [https://grafana.com/docs/](https://grafana.com/docs/)

