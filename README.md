# Proyecto Integrador Final - PIN

## Integrantes Grupo 21:
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
   - En caso de haberlos
8. [Referencias](#referencias)
   - Documentación utilizada
   - Enlaces útiles

---

## Introducción

El presente proyecto tiene como objetivo integrar una solución DevOps utilizando tecnologías modernas como Kubernetes, Docker, Jenkins, Prometheus y Grafana. Este proyecto busca la implementación de un sistema de monitoreo de aplicaciones y servicios desplegados en un clúster Kubernetes.

La solución fue diseñada para proporcionar una infraestructura automatizada que permite recolectar y visualizar métricas de los servicios del clúster, con un enfoque particular en la monitorización continua mediante herramientas de recolección de datos y su visualización en tiempo real.

---

## Diagrama de Arquitectura

La arquitectura del proyecto se basa en la integración de las siguientes herramientas clave:

- **Minikube**: Clúster de Kubernetes local.
- **Docker**: Plataforma de contenedores.
- **Jenkins**: Para la integración y entrega continua.
- **Prometheus**: Sistema de monitoreo de métricas.
- **Grafana**: Herramienta de visualización de métricas.

El diagrama de arquitectura ilustra cómo estas herramientas interactúan entre sí para crear una solución eficiente y escalable.

---

## Herramientas Utilizadas

- **Minikube**: Para crear un clúster de Kubernetes local.
- **Docker**: Utilizado para crear contenedores de aplicaciones.
- **Jenkins**: Plataforma para gestionar los pipelines de integración continua y despliegue continuo (CI/CD).
- **GitHub**: Repositorio para almacenar el código fuente y las definiciones de los pipelines.
- **Prometheus**: Herramienta de monitoreo para recolectar métricas en tiempo real.
- **Grafana**: Plataforma de visualización de métricas que se conecta a Prometheus.

---

## Proceso de Implementación

### 1. **Configuración del Clúster Local**
Se configuró un clúster local de Kubernetes utilizando Minikube. Esto permitió el desarrollo y prueba de los servicios en un entorno aislado.

- Se configuró la IP del clúster para permitir la resolución del dominio `front-pinfinal.com`.

### 2. **Configuración de Jenkins**
Jenkins fue instalado y configurado con los siguientes pasos:

- Instalación de plugins necesarios para interactuar con Docker y Kubernetes.
- Conexión a GitHub para obtener las definiciones de los pipelines y el código fuente.

### 3. **Ejecución de Pipelines**
Se automatizaron los siguientes procesos mediante Jenkins:

- **deploy-nginx-exporter-cluster-pin-final-mundose**: Despliegue de un contenedor **NGINX Exporter** para la recolección de métricas de NGINX.
  
- **prometheus-cluster-monitoreo-pin-final-mundose**: Despliegue de Prometheus y Node Exporter para recolectar métricas de servicios y nodos en el clúster.

- **grafana-cluster-monitoreo-pin-final-mundose**: Despliegue de Grafana y configuración para conectarse a Prometheus y visualizar las métricas.

---

## Monitoreo y Visualización

**Prometheus** se configuró para recolectar métricas de los servicios y nodos del clúster. La interfaz de Prometheus se encuentra disponible en la siguiente URL:

- **Prometheus**: [http://dev-env.grupo13.com/services/prometheus](http://front-pinfinal.com/services/prometheus)

**Grafana** fue configurado para visualizar las métricas de Prometheus en dashboards interactivos. La interfaz de Grafana está disponible en:

- **Grafana**: [http://dev-env.grupo13.com/services/grafana](http://szebastian001/front-pinfinal/services/grafana)

---

## Links y Repositorios

- **Repositorio del Proyecto**: [GitHub - DevOps Pin Final](https://github.com/Szebastian/Devops-Pin-Final)
- **URL de Grafana**: [http://dev-env.grupo13.com/services/grafana](http://szebastian001/front-pinfinal/services/grafana)
- **URL de Prometheus**: [http://dev-env.grupo13.com/services/prometheus](http://front-pinfinal.com/services/prometheus)

---

## Resolución de Problemas

Durante la implementación se presentaron los siguientes problemas:

- **Problema de conexión entre Jenkins y Kubernetes**: Se resolvió ajustando la configuración del archivo kubeconfig para asegurar que Jenkins pudiera acceder al clúster de Minikube.
  
- **Problema con la conexión de Grafana a Prometheus**: Inicialmente, Grafana no lograba conectarse a Prometheus debido a configuraciones erróneas de URL y credenciales. Estos problemas fueron solucionados revisando y ajustando las configuraciones en ambos servicios.

---

## Referencias

- **Documentación de Docker**: [https://docs.docker.com/](https://docs.docker.com/)
- **Documentación de Kubernetes**: [https://kubernetes.io/docs/](https://kubernetes.io/docs/)
- **Documentación de Jenkins**: [https://www.jenkins.io/doc/](https://www.jenkins.io/doc/)
- **Documentación de Prometheus**: [https://prometheus.io/docs/](https://prometheus.io/docs/)
- **Documentación de Grafana**: [https://grafana.com/docs/](https://grafana.com/docs/)

---

Este documento describe detalladamente los pasos y herramientas utilizadas para implementar una solución DevOps completa con integración continua, despliegue continuo y monitoreo utilizando las tecnologías mencionadas.
