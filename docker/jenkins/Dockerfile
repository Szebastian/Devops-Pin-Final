# Usa la imagen oficial de Jenkins LTS como base
FROM jenkins/jenkins:lts

# Configuración de usuario y contraseña de Jenkins
ENV JENKINS_USER admin
ENV JENKINS_PASS admin

# Instalación de Docker
USER root
RUN apt-get update && \
    apt-get -y install apt-transport-https ca-certificates curl gnupg2 software-properties-common && \
    curl -fsSL https://download.docker.com/linux/$(. /etc/os-release; echo "$ID")/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg && \
    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/$(. /etc/os-release; echo "$ID") $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list && \
    apt-get update && apt-get -y install docker-ce && \
    usermod -aG docker jenkins

# Instalación de kubectl
RUN curl -LO --retry 5 --retry-delay 10 "https://dl.k8s.io/release/$(curl -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" && \
    install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl && \
    rm kubectl

# Copiar archivo de configuración de Kubernetes
COPY config /var/jenkins_home/.kube/config

# Asegurar permisos correctos
RUN mkdir -p /var/jenkins_home/.kube && \
    chown -R jenkins:jenkins /var/jenkins_home/.kube

# Configuración de entorno para Kubernetes
ENV KUBECONFIG=/var/jenkins_home/.kube/config

# Exponer puerto predeterminado de Jenkins
EXPOSE 8080

# Punto de entrada
ENTRYPOINT ["jenkins"]
