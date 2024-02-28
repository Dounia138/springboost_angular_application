# Demo  + MySQL + Docker

## Prerequis 

- Docker : (https://www.docker.com/)
- Docker Compose : (https://docs.docker.com/compose/)

## Mise en place

1. Clone le repo :

    ```bash
    git clone https://github.com/Dounia138/springboost_angular_application.git
    ```

2. Construire et demarrer le projet

    ```bash
    docker-compose up -d
    ```

3. L'application springboot est sur [http://localhost:8080] et l'application Angular  [http://localhost:4200]



## Details :


### Springboot

L'application springboot est generéepar  (https://start.spring.io/)

## Contexte

On utilise l'image Docker officielle de Gradle version 8.6.0 avec JDK 17 comme image de base.
`CMD ["./gradlew", "bootRun"]` : Spécifie la commande par défaut à exécuter lorsque le conteneur démarre.

### Angular

L'application Angular est sur [http://localhost:4200]

## Contexte

L'application à été telechager depuis 
(https://angular.io/)

Le dockerfile est basé sur l'image node, on installe les dependances et run l'application avec la commande  `npm start`

## Warning 

Si jamais vous rencontrez une erreur liée au dockerfile.angular en lançant le docker-compose, vous devez vous placer dans le répertoire angular en exécutant la commande `cd angular` dans votre terminal, puis exécuter la commande `npm run build` car il y a une question à laquelle il faut répondre, et le Dockerfile, dans notre cas, ne gère pas ces interactions.

### Base de donnés (MySQL)

## Contexte

Nous utilisons l'image MySQL, et on definit le mot de passe et le nom de la base de données dans le fichier `docker-compose.yml`.
Nous montons le conteneur sur le même réseau que l'application springboost, afin que qu'elle puisse accéder à la base de données en utilisant le nom du conteneur comme hôte (`db`).
