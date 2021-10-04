## Architecture micro-services vs architecture monolithique
Dans ce depôt github nous allons voir la comparaison entre l'architecture d'une application monolithique et micro services.

### Qu'est-ce qu'une application monolithique ?
---
Une application monolithique est une application qui est développée en un seul bloc (war, jar, Ear, dll), avec une même technologie et déployée dans un serveur d'application.

### Architecture d'une application monolithique
---
Passons en revue le schéma architectural pour mieux comprendre.
Je vais expliquer l'un des exemples du monde réel qui est n'importe quel site d'achat en ligne 
comme Flip-Kart, Amazon, E Bay qui s'est développé auparavant avec une approche monolithique.<br/>
Supposons que j'ai peu de services, ce qui est :<br/>
* Services de gestion de compte 
* Services d'inventaire/panier 
* Service de paiement 
* Services d' expédition 
* Service de notification

![Architecture_monolithique](https://user-images.githubusercontent.com/75081354/135835478-e59a299d-fc0a-469f-9f98-8eefe8302d50.jpg)

Voir le diagramme ci-dessus, je développe les 4 services, puis je les ai tous empaquetés 
et déployés en une seule WAR, et j'accède aux services à l'aide de l'appel API Rest.

### Problèmes des applications monolithiques
---
Les principaux problèmes des applications monolithiques sont :<br/>
* Elles centralisent tous les besoins fonctionnels
* Elle sont réalisées dans une seule technologie.
* Chaque modification necessite de :
	* Tester les régressions
	* Redéplyer toute l'application
* Difficile à faire évoluer au niveau fonctionnel
* Livraison en bloc (Le client attend beaucoup de temps pour commencer à voir les premieres versions)

### Les micro services
---
* Les micro services sont une approche d'architecture et de développement d'une application composées de petits services.
* L'idée étant de découper un grand problème en petites unités implémentée sous forme de micro-services
* Chaque service est reponsable d'une fonctionnalité
* Chaque micro-service est développé, testé et déployé séparement des autres
* Chaque micro-service est développé en utilisant une technologie qui peut être différente des autres(Java, C++, C#, PHP, NodeJS, Python...)
* Chaque service tourne dans un processus séparé
* Utilisant des mécanismes de communication légers (REST)
* La seule relkation entre les différentes micro-services est l'échange de données effectué à travers les différentes APIs qu'ils exposent (SOAP, REST, RMI, CORBA, JMS, MQP, ...)
* Lorsqu'on les combinent, ces micro-services peuvent réaliser des opérations très complexes

Un micro-service combine les trois couches "**métier, technique et données**" en une seule, accessible via des API.

### Aspects clefs des micro service
---
* Ils sont faiblement couplés puisque chaque micro service est physiquement séparé des autres
* Indépendance relative entre les différentes équipes qui développement les différents micro services
* Facilité des tests et du déploiement
* Livraison continue
* S'apprête bien à au processus du GL : TDD (Test Driven Développement) et les méthodes agiles

### Diagramme d'architecture de micro services
---
![Archiitecture_microservice](https://user-images.githubusercontent.com/75081354/135835548-c79dd7d8-a9b1-43fb-bccc-ac963d868712.jpg)

Voir selon le schéma, chaque service est interconnecté mais tous les modules sont séparés ici signifie une WAR indépendante.<br/>

Tous les 3 services mentionnés ci-dessus ont leur propre développement et leur propre package et déployés, 
nous pouvons dire que chaque service est un micro-service.<br/>

Il existe une passerelle API qui gère tous les micro-services et agit comme un point d'entrée frontal.<br/>

Selon le diagramme ci-dessus, j'ai développé 3 micro-services, car je ne vais pas tout déployer 
comme une seule WAR, alors réfléchissez à la façon dont puis-je obtenir des fonctionnalités 
d'un service, signifie comment communiquer d'un service à un autre.<br/>

C'est pourquoi de nombreux tiers donnent la main pour prendre en charge l'architecture des micro-services.

### Aperçu de deux architectures
---
Jetons un coup d'œil au diagramme architectural combiné du service monolithique et micro services.<br/><br/>
![Archi_mixte](https://user-images.githubusercontent.com/75081354/135836235-6406078b-2f11-440b-9b27-79dba6fb410e.png)
