# ping-test

Este repositorio ping-test centraliza la documentación del proyecto completo, que está compuesto por tres repositorios individuales (challenge1, challenge2 y challenge3) que trabajan juntos para completar diferentes aspectos del proyecto.

Cada uno de estos repositorios tiene su propio código y documentación, pero aquí se proporciona una visión general de cómo interactúan entre sí y una guía para ejecutar el proyecto en su totalidad.

## Requisitos para ejecutar el proyecto entero
1. Tener una cuenta de [GitHub](https://github.com/).
2. Tener una cuenta en [Azure](https://azure.microsoft.com/).
3. Tener una cuenta en [Terraform Cloud](https://app.terraform.io/app).

## Estructura del Repositorio
Este repositorio está estructurado de la siguiente manera:

        ping-test/
        ├── README.md    --------> Documentación general del proyecto
        ├── challenge1/  --------> Directorio para el Repositorio 1
        │   └── link.md  --------> Enlace al Repositorio 1 y su descripción
        ├── challenge2/  --------> Directorio para el Repositorio 2
        │   └── link.md  --------> Enlace al Repositorio 2 y su descripción
        └── challenge3/  --------> Directorio para el Repositorio 3
            └── link.md  --------> Enlace al Repositorio 3 y su descripción

## Descripción de los elementos:
README.md: Contiene una visión general de cómo ejecutar el proyecto completo y cómo los tres repositorios se integran entre sí. Proporciona instrucciones generales para configurar y ejecutar el sistema.

challenge1/link.md, challenge2/link.md, challenge3/link.md: Cada uno de estos archivos contiene el enlace directo al repositorio correspondiente donde se aloja el código.

## ¿Cómo funciona el proyecto?
El proyecto completo se ejecuta utilizando tres repositorios que colaboran entre sí. Este repositorio de documentación sirve para enlazar toda la información y guiar sobre cómo configurar y ejecutar cada parte del proyecto.

## Pasos para la Ejecución:
### Verificar que todas las variables estan bien introducidas.
En todos los challenges hay una serie de variables que deben ser configuradas correctamente antes de que el proyecto pueda ser funcional. Comprueba, siguiendo los README de cada challenge, que se están configurando las variables adecuadamente.

### Subir el Helm Chart al ACR:

El primer paso para ejecutar el proyecto es subir el Helm chart del challenge1 a un Azure Container Registry (ACR). El ACR de referencia segun el enunciado.

Puedes hacerlo ejecutando el siguiente comando de Helm:

        helm push ./chart oci://<tu-acr>.azurecr.io/charts

### Clonar el repositorio del Challenge 2:

Una vez que el Helm chart esté en el ACR, clona el repositorio correspondiente al Challenge 2 en tu cuenta de GitHub. Este repositorio contiene el código necesario para automatizar la copia de charts entre registros ACR.

Usa el siguiente comando para clonar el repositorio:

        git clone https://github.com/<tu-usuario>/<repo-challenge2>.git

### Configurar GitHub Actions para el Despliegue:

El Challenge 3 contiene el código de GitHub Actions que se encargará de desplegar el Helm chart en un clúster de AKS.

Para configurar las GitHub Actions, tienes la documentación [aquí](https://docs.github.com/es/actions).

### Advertencias
El código del challenge1 ha sido probado en un entorno local usando Minikube, pero no ha sido ejecutado en un entorno en la nube.

El Challenge 2 no se ha podido probar completamente debido a la falta de tiempo.

Por razones obvias, el challenge3 tampoco ha sido probado en su totalidad.