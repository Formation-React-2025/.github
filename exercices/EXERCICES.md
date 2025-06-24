# Formation React 2025

## Exercice 1

### Initialisation d'un nouveau projet React
- Lancer la commande ```npx create-react-app exercice_1```
- Dans le dossier ```exercice_1``` lancer les commande ```npm install``` (ou ```npm i```) puis ```npm start```

### Création d'un premier composant React
- Dans le package ```./src/components/exercice-1```. créer le composant ```Exercice1``` dont le comportement est le suivant :
  - Le composant affiche un header avec le titre « Exercice 1 »
  -	Le composant affiche en contenu « Hello world ! »
  -	Le composant affiche un footer avec la date et l’heure

- Dans le fichier ```./src/App.js``` supprimer le code retourné et appeler le composant.


Note : on pourra utiliser la fonction javascript ```toLocalDateString``` de ```Date``` pour afficher la date et l’heure au format voulu (voir [Date.prototype.toLocaleString()](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleDateString)).

<u>Exemple :</u>
```
new Date().toLocaleDateString('fr-FR', {
    weekday: 'long',
    year: 'numeric',
    month: 'long',
    day: 'numeric',
    hour: 'numeric',
    minute: 'numeric',
    second: 'numeric',
})
```

## Exercice 2

### Initialisation du projet
Plusieurs possibilités :
- Initialiser le projet via la commande ```npx create-react-app```
- Continuer sur le même projet
- Télécharger le projet initialisé depuis le GitHub [Formation React 2025](https://github.com/orgs/Formation-React-2025/repositories) :
  - ```git clone https://github.com/Formation-React-2025/exercice_2.git```

### Création d'un composant avec des props
- Lancer la commande ```npm install prop-types@15.8.1```.
 
- Dans le package ```./src/components/exercice-2```, créer le composant ```Exercice2``` dont le comportement est le même que le composant ```Exercice1``` aux différences suivantes :
  -	Le titre du header est maintenant reçu en props
  -	Le contenu correspond à la props ```children```
 
- Dans le fichier ```./src/App.jsx```, appeler le composant.

<u>Note :</u> par la suite, nous pourrons duppliquer ce composant dans ```./src/components/layout/exercice-layout/ExerciceLayout``` afin de le réutiliser.

## Exercice 3

### Initialisation du projet
Plusieurs possibilités :
- Initialiser le projet via la commande ```npx create-react-app```
- Continuer sur le même projet
- Télécharger le projet initialisé depuis le GitHub [Formation React 2025](https://github.com/orgs/Formation-React-2025/repositories) :
  - ```git clone https://github.com/Formation-React-2025/exercice_3.git```

### Création d'un composant avec state
- Dans le package ```./src/components/exercice-3```, créer le composant ```Exercice3```.
- Le composant retournera un formulaire avec deux champs de saisie de type ```text``` et un bouton de type ```submit```.
-  Les champs seront ```uncontrolled```, ```required``` et leurs valeurs seront gérées au travers d’un « state » React.
-  Les libellés des champs seront les suivants :
    - « Nom »
    - « Prénom »
- Le bouton portera la mention « Enregistrer ».

- À la soumission du formulaire, contrôler que les champs obligatoires sont bien renseignés. Si ce n’est pas le cas, afficher les champs en rouge avec un message « Le champ est obligatoire ».

- Dans le fichier ```./src/App.jsx```, appeler le composant.

<u>Notes :</u> afin de ne pas propager l’évènement de validation du formulaire, on pourra utiliser la méthode ```e.preventDefault()```.

Notions : CSS, state

## Exercice 4 – Découpage

### 1 - Initialisation du projet
Plusieurs possibilités :
- Initialiser le projet via la commande ```npx create-react-app```
- Continuer sur le même projet
- Télécharger le projet initialisé depuis le GitHub [Formation React 2025](https://github.com/orgs/Formation-React-2025/repositories) :
    - ```git clone https://github.com/Formation-React-2025/exercice_4.git```

### 2 - InputText
- Créer un composant ```InputText``` » dans le package ```./src/components/input/input-text``` ».
- Le composant retourne un ```uncontrolled``` input de type ```text``` dont la valeur est passée en props.
- Le composant prend en entrée les props suivantes :

|         Nom         | Description                                                                   |      Type      |  Required   | Valeur par défaut |
|:-------------------:|-------------------------------------------------------------------------------|:--------------:|:-----------:|:-----------------:|
|     ```label```     | Label du champ                                                                |  ```string```  | ```true```  |         -         |
|     ```value```     | Valeur de l'input                                                             |  ```string```  | ```false``` |  ```undefined```  |
| ```onValueChange``` | Fonction de callback ```(value: string) => void``` à exécuter lors d'un input | ```Function``` | ```false``` |  ```undefined```  |
|     ```name```      | Name de l'input                                                               |  ```string```  | ```false``` |  ```undefined```  |
|     ```error```     | Texte à afficher en cas d'erreur                                              |  ```string```  | ```false``` |  ```undefined```  |
|   ```disabled```    | Pour désactiver le champ                                                      | ```boolean```  | ```false``` |    ```false```    |
|   ```required```    | Pour rendre le champ obligatoire                                              | ```boolean```  | ```false``` |    ```false```    |

### 2 - LabelButton
- Créer un composant ```LabelButton``` dans le package ``` ./src/components/input/buttons/label-button```.
- Le composant retourne un button et prend en entrée les props suivantes :

|      Nom       | Description                                                                                     |      Type      |  Required   | Valeur par défaut |
|:--------------:|-------------------------------------------------------------------------------------------------|:--------------:|:-----------:|:-----------------:|
|  ```label```   | Label du bouton                                                                                 |  ```string```  | ```true```  |         -         |
|   ```type```   | Définit le type de button (```submit```, ```button``` ou ```reset```)                           |  ```string```  | ```false``` |  ```'button'```   |
| ```onClick```  | Fonction de callback ```(event: HtmlEventt) => void``` à exécuter lors d'un clic sur le bouton  | ```Function``` | ```false``` |  ```undefined```  |
| ```disabled``` | Pour désactiver le champ                                                                        | ```boolean```  | ```false``` |    ```false```    |

### 3 - Découpage et réutilisation de composants
- Dans le package ```./src/components/exercices-exercice-4```, re-créer le formulaire de l’exercice 3 en utilisant les nouveaux composants ```InputText``` et ```LabelButton```.
