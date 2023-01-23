# Examen AMT 2023

## Matière de l'examen 
Il s'agit de la mise en oeuvre d'une api avec Springboot et d'un client de test BDD avec Cucumber.

Dans une approche top-down (description api -> code), vous devrez générer à partir d'un fichier OpenAPI :
 - des intertaces et des DTO pour l'API Springboot
 - d'un client et des DTO pour le client de test BDD Cucumber

puis coder l'API et les tests.

A cet effet, ce dépôt sera cloné dans votre dépôt de rendu (voir ci-dessous). 
Il contient un endpoint « quotes » qui sert d’exemple et permet la vérification
du processus de développement et de test. 

Une seule API sera développée (pas de microservices).
Il ne sera pas demandé d'en sécuriser l'accès (pas de JWT).

## Contraintes pour le codage

Il sera tenu compte dans l'évaluation du respect des principes de l'architecture REST
(ressources, routes, méthodes d'accès, statut HTTP, sérialisation JSON), 
du processus de développement
et de l’architecture (packages, conventions de nommage) implémentée dans ce projet 
pour le point d'accès "Quotes" à titre d’exemple. 

Votre api (fichier yaml) doit être décrite de façon complète (statuts d'erreurs, ...) et bien commentée.

Votre code source Java devra être "propre", indenté, nettoyé des divers essais abandonnés ou traces inutiles.
Vous pouvez laisser du code incomplet mais il ne doit pas empêcher le deploiement 
et l'utilisation de ce qui fonctionne en commentant, par exemple, le code gênant.
En dehors de cela, il n'est pas demandé de commenter le code. 

Vos scénarios Cucumber doivent être rédigés selon les bonnes pratiques BDD, 
en respectant le rôle des mots clefs, avec des phrases simples et précises, 
et en utilisant les moyens permettant de ré-utiliser  et de réduire le nombre de scénarios
et de tests (variables, data tables, scenario outline, ...) .

Laissez dans votre projet le point d'accès "Quotes" opérationnel.
Laissez également le README en l'état : utilisez la feuille d'énoncé pour nous transmettre 
vos explications ou vos commentaires.

L'importation de librairies externes, d'autres dépendances ou plug-ins que ceux déjà inclus est **interdite**.
Vous êtes très fortement encouragés à concevoir votre code "as simple as possible",
sans création d'interfaces ni de classes abstraites ou génériques.

En début d’examen, un fichier **data-all.sql** sera déposé dans le dossier racine 
du dépôt https://github.com/patricklac/amt-exa-ETUDIANT.
Il contient des "insert" de données pour les tables que vous ferez créer par JPA au déploiement
et qui vous serviront pour tester votre application (swagger-ui ou Cucumber).

Au fur et à mesure de votre développement, recopiez dans le fichier « data.sql » du module Springboot
les « insert » correspondant aux entités et donc aux tables que vous aurez définies.
Faites en sorte que les tables générées correspondent exactement à ces « insert » 
(note: JPA traduit le camelCase en utilisant "_" comme séparateur, par exemple aaaBbb en aaa_bbb). 
Si vous n'y arrivez pas, vous pouvez et vous devez ajuster ces "insert". 
Mais dans tous les cas, la structure de données générée doit rester normalisée 
et garantir l’intégrité des données par des contraintes de clefs primaires et étrangères.

Les accès aux données doivent être réalisés de façon pertinente et optimisée en utilisant JPA. 
Vous ne devez pas, par exemple, charger plus de données que nécessaire
ou multiplier les accès alors qu'un seul suffirait. 
Votre code devrait rester performant avec une base de données très volumineuse.

## Déroulement de l'épreuve (durée: 2 heures)

Pendant l'épreuve, vous avez droit à la consultation et à l’utilisation de tous les documents accessibles sur votre PC 
ou sur Internet mais il est **strictement interdit** de demander de l’aide à l’extérieur 
ou d’échanger de l’information directement ou indirectement entre étudiants. 

Vous ne devez pas déposer votre travail ou des éléments de celui-ci ailleurs que sur le dépôt prévu 
pour le rendu de l’examen, en veillant à ce qu’il reste confidentiel.

Au cours de l'épreuve, l'enseignant vous demandera de réaliser au moins un commit et push de votre projet en l’état
sur la branche master de votre dépôt chaque 30 minutes environ (messages de commit: "commit1", "commit2", "commit3"). Vérifiez que tous vos fichiers soient bien gérés par GIT. 
**Un manquement vaudra pénalité**. Ces commit ne seront examinés qu’en cas de suspicion de tricherie.
Vous êtes encouragés à réaliser des commit et push supplémentaires, à votre convenance. 

Le travail devra être rendu par un dernier commit (message de commit: "rendu") et push à l'issue de l'épreuve.
Vous rendrez également la feuille d'énoncé avec votre nom et votre évaluation point par point de ce que vous avez réalisé. 

## _A réaliser avant la fin du semestre_ : directives pour la préparation du projet initial pour l'épreuve
 - Dans la suite de ces directives, la chaine de caractère ETUDIANT devra être remplacée à plusieurs endroits. Utilisez à chaque fois le même mot :
   - Votre propre nom de famille (sans le prénom, **en majuscules**, sans accentuation)
   - Si votre nom de famille est composé, n'utilisez que le premier mot, sauf s'il n'est pas unique dans la classe (acollez-y dans ce cas un différenciateur)
 - git clone amt-exa-ETUDIANT
 - Changez le nom du dossier amt-exa-ETUDIANT en remplaçant ETUDIANT par votre nom
 - Changez les noms des sous-dossiers amt-exa-ETUDIANT-api et amt-exa-ETUDIANT-spec en remplaçant ETUDIANT par votre nom
 - Avec un éditeur de texte, modifiez les fichiers pom.xml du dossier racine et des sous-dossiers api et spec pour remplacer partout ETUDIANT par votre nom
 - Importez sous IntelliJ le projet (maven) qui contient 2 modules, un module api pour Springboot
et un module spec pour le client BDD
   - Affectez un Java JDK 17 (File / Project structure / Project /SDK )
   - Via le menu contextuel "Refactor / Rename", modifiez le nom de la racine des packages des modules api et spec en remplaçant ETUDIANT par votre nom
 - Vérifiez le bon fonctionement du endpoint "quotes" inclus dans le projet comme décrit plus loin dans ce readme
 - Créez un dépôt **privé** sur GITHUB de nom amt-exa-ETUDIANT, ETUDIANT remplacé par votre nom
 - Mettez à jour le GIT remote de votre projet
   - soit en ligne de commande GIT dans votre dossier: git remote --set-upstream origin [url de votre dépôt privé]
   - soit avec Intellij, menu git / manage remote
 - Ajoutez tous les fichiers du projet dans GIT et faites un premier commit avec le message "initial" et push en utilisant GIT en ligne de commande ou avec IntellJ
 - **Vérifiez le contenu de votre dépôt privé et n'y touchez plus jusqu'à l'examen**
 - Invitez nous **au plus tard lors de la dernière séance AMT du semestre** à votre dépôt privé comme collaborateur via Settings / collaborators de GITHUB :
   - nicolas.glassey@cpnv-vd.ch
   - patrick.lachaize@gmail.com

## Vérification du bon fonctionement avec le endpoint "quotes" inclus dans le projet
 ### Module api
  - Gérération du dossier target avec "maven clean package" dans le dossier api 
( IntellJ: fenêtre Maven, onglet ...api/Lifecyle).
Ne pas utiliser cette commande au niveau du projet car le fichier yaml ne sera pas trouvé
  - Déclaration "Generated Source Root" du dossier target/generated-sources/openapi/src/main/java 
    via le menu contextuel "Mark directory as" sur ce dossier
  - Lancement du main Springboot (Swagger2SpringBoot)
  - L'interface utilisateur swagger-ui est accessible à http://localhost:9090/api
  - La base de donnée H2 est accessible à http://localhost:9090/api/h2-console
      url: jdbc:h2:mem:testdb username:sa pas de password
  ### Module spec
  - Gérération du dossier target avec "maven clean package" dans le dossier spec (IntellJ: fenêtre Maven, onglet ...spec/Lifecycle)
  - Si Springboot tourne, les tests BDD doivent s'exécuter sans erreurs au cours de l'exécution de Maven
  - Déclaration "Generated Source Root" du dossier target/generated-sources/openapi/src/main/java 
  - La Feature Cucumber du dossier src/test/resources/features/quotes.feature doit être exécutable sous IntelliJ
  
  ## Cycle de développement et de réponses aux questions de l'épreuve
  - Modifier le fichier OpenAPI "api.yaml" sous src/main/resource des 2 projets (copies identiques)
  - Api Springboot
    - Relancer "maven clean package" du module api
    - Développer ou adapter les controlleurs, les DTO et les classes liées dans l'api Springboot
    - Si vous avez ajouté ou modifié des entités, vous pouvez initialiser des données 
      dans le fichier data.sql de src/main/resource
    - Relancer Sprigboot et faire quelques tests manuels avec swagger-ui
  - Tests BDD cucumber (en mode TDD, les 2 premières étapes peuvent être effectuées avant le développement de l'api)
    - Relancer "maven clean package" du module spec, les tests seront peut-être en erreur et peuvent être skippés
    - Développer ou adapter les features Cucumber et les steps pour les nouvelles fonctionalités
    - Exécuter les tests sous IntelliJ et relancer "maven clean package" du module spec pour exécuter les tests avec Maven
  
    
