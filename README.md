# Architecture TP Microservices – Spring Boot, Eureka, Gateway & Docker

Ce projet illustre une architecture microservices complète basée sur **Spring Boot**, comprenant :  
- Un serveur de découverte de services **Eureka**
- Plusieurs microservices indépendants (`car`, `client`, etc.)
- Une API Gateway centralisée
- Un mesh de services avec **Consul**
- Un stockage de données via **MySQL**
- Une interface de gestion BDD avec **phpMyAdmin**
- Un outil d’analyse de qualité de code avec **SonarQube**
- Un déploiement automatisé grâce à **Docker Compose**

---

## 🏗️ Structure du projet

- **car/** : Microservice de gestion des véhicules (Spring Boot, Data JPA, REST, Eureka Client)
- **client/** : Microservice de gestion des clients/utilisateurs (Spring Boot, Actuator, JPA, Eureka Client)
- **gateway/** : Microservice API Gateway (Spring Cloud Gateway, Eureka Client)
- **server_eureka/** : Serveur de découverte de services (Spring Cloud Eureka Server)
- **deploy/** : Scripts et fichiers Docker Compose pour démarrer l’architecture complète
- **sonarqube-compose.yml** : Déploiement d’un SonarQube pour l’analyse de la qualité du code

---

## ⚙️ Architecture technique

![Architecture microservices - Spring Boot + Docker](https://raw.githubusercontent.com/mtdvio/every-programmer-should-know/master/media/microservices.png)

- **Eureka** assure le service discovery pour tous les microservices.
- **Spring Cloud Gateway** centralise les points d’entrée API (reverse proxy et router).
- **Consul** gère la configuration dynamique et le mesh de services.
- **MySQL** sert pour le stockage ; **phpMyAdmin** permet la gestion via interface web.
- **SonarQube** permet le contrôle continu de la qualité via CI.

---

## 🚀 Démarrage rapide

**Prérequis** :
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

### 1. Clone du projet

```bash
git clone https://github.com/RadouaneAitSaid123/architecture-tp32.git
cd architecture-tp32
```

### 2. Configuration

Dans `deploy/.env`, configure les variables (mots de passe, ports, BDD...) si besoin.

### 3. Lancement complet (multi-services)

```bash
cd deploy
docker-compose up --build
```

- L’API Gateway sera accessible sur le port `8888` (par défaut)
- Les microservices client et car sur les ports `8088` et `8089`
- Eureka à `http://localhost:8761`
- Consul à `http://localhost:8500`
- phpMyAdmin à `http://localhost:8081`

### 4. Arrêt et nettoyage

```bash
docker-compose down
```

---

## ✏️ Fonctionnalités principales

- **Scalabilité** : architecture modulaire microservices
- **Sureté** : gestion centralisée via Eureka et Gateway
- **Monitoring** : Spring Boot Actuator, Consul et Eureka dashboards
- **Testabilité** : profils de conf intégrés (MySQL/H2), scripts tests inclus
- **Qualité** : Intégration SonarQube pour l’analyse du code

---

## 📂 Arborescence (extrait)

```
.
├── car/
│   ├── src/...
│   └── pom.xml
├── client/
│   ├── src/...
│   └── pom.xml
├── gateway/
│   ├── src/...
│   └── pom.xml
├── server_eureka/
│   ├── src/...
│   └── pom.xml
├── deploy/
│   ├── docker-compose.yml
│   └── .env
├── sonarqube-compose.yml
└── README.md
```

---

## 👨‍💻 Contribution

1. Fork, clone et crée une branche pour ta feature/bugfix.
2. Teste tes changements.
3. Ouvre une Pull Request !

---

## 👤 Auteur

- Radouane Ait Said  
[GitHub - RadouaneAitSaid123](https://github.com/RadouaneAitSaid123)

---

## 📚 Liens utiles

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring Cloud](https://spring.io/projects/spring-cloud)
- [Consul](https://www.consul.io/)
- [Docker Compose](https://docs.docker.com/compose/)
- [SonarQube](https://www.sonarqube.org/)
