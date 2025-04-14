# 🛒 TP J2EE - Partie 2 : Gestion des Produits avec Spring Boot

Ce projet fait partie d’un TP de J2EE basé sur Spring Boot, et permet de manipuler les concepts de base d'une application CRUD simple avec une entité `Product`, un repository, et la connexion à une base MySQL. Il sert également à pratiquer la configuration de projet avec Maven et Spring Data JPA.

---

## 📁 Structure du projet

```
src/
├── main/
│   ├── java/org/example/tp2/
│   │   └── entities/Product.java       # Entité JPA représentant un produit
│   └── resources/
│       └── application.properties      # Configuration du projet
```

---

## 🧱 Entité `Product.java`

```java
@Entity
@Table(name = "Product")
@Data @AllArgsConstructor @NoArgsConstructor @Builder
public class Product {
    @Id @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private double price;
    private int quantity;
}
```

Cette classe représente les produits avec les champs suivants :
- `id` : identifiant auto-généré
- `name` : nom du produit
- `price` : prix du produit
- `quantity` : quantité disponible

Les annotations **Lombok** facilitent la création de getters/setters, constructeurs et builders.

---

## ⚙️ Fichier `application.properties`

Ce fichier configure les éléments principaux du projet :

```properties
spring.application.name=tp2
server.port=8080

spring.datasource.url=jdbc:mysql://localhost:3306/products-db?createDatabaseIfNotExist=true&useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=

spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MariaDBDialect
debug=true
```

La base de données **MySQL** est utilisée. Si la base `products-db` n’existe pas, elle sera automatiquement créée.

---

## 📦 Dépendances utilisées (dans `pom.xml`)

Le projet utilise les dépendances suivantes :
- `spring-boot-starter-data-jpa` : accès aux données avec JPA
- `spring-boot-starter-web` : création d’API REST ou de pages web
- `mysql-connector-j` : pour connecter l’application à MySQL
- `lombok` : pour réduire le code boilerplate

---

## 🚀 Lancement du projet

1. S’assurer que MySQL est lancé sur `localhost:3306`.
2. Le schéma `products-db` est généré automatiquement.
3. Lancer le projet dans IntelliJ ou via `mvn spring-boot:run`.
4. Une fois lancé, l’application tourne sur [http://localhost:8080](http://localhost:8080)

---

## 👩‍🎓 Réalisé par

Projet réalisé par **Samia Fykri** dans le cadre du TP2 en J2EE avec Spring Boot.
