# Formation React 2025

## Exercice 1 - Création d'un premier composant React

### Initialisation d'un nouveau projet React
- Lancer la commande ```npx create-react-app exercice_1```
- Dans le dossier ```exercice_1``` lancer les commande ```npm install``` (ou ```npm i```) puis ```npm start```

### Création d'un premier composant React
- Dans le package ```./src/features/exercices/pages/exercice-1```. créer le composant ```Exercice1Page``` dont le comportement est le suivant :
  - Le composant affiche un header avec le titre « Exercice 1 - Création d'un premier composant React »
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

## Exercice 2 - Création d'un composant avec props

### 1 - Initialisation du projet
Plusieurs possibilités :
- Continuer sur le même projet
- Télécharger le projet initialisé depuis le GitHub [Formation React 2025](https://github.com/orgs/Formation-React-2025/repositories) :
  - ```git clone https://github.com/Formation-React-2025/exercice_2.git```

### 2 - Création d'un composant avec des props
- Lancer la commande ```npm install prop-types@15.8.1```.
 
- Dans le package ```./src/features/exercices/pages/exercice-2```, créer le composant ```Exercice2Page``` dont le comportement est le même que le composant ```Exercice1Page``` aux différences suivantes :
  -	Le titre du header est maintenant reçu en props
  - Le titre est "Exercice 2 - Création d'un composant avec props"
  -	Le contenu correspond à la props ```children```
 
- Dans le fichier ```./src/App.jsx```, appeler le composant.

<u>Note :</u> par la suite, nous pourrons dupliquer ce composant dans ```./src/components/layout/page-layout/PageLayout.jsx``` afin de le réutiliser.

### 3 - Mise à jour de variable
- Dans le package ```./src/components/input/buttons/on-click-button```, créer un composant `OnClickButton` :
- Le composant initialise une variable locale à 0
- Le composant déclare une fonction dont l'exécution incrémente la variable
- La fonction doit afficher en console (`console.log(.)`) la valeur de la variable avant incrémentation et après incrémentation
- Le composant retourne un bouton, qui, lorsque l’on clique dessus, exécute la fonction.
- Le label du bouton est la variable

- Dans le composant `Exercice2Page`, appeler le composant `OnClickButton`, ouvrer la console du navigateur (`F12`) et cliquez sur bouton.
- Que constatez-vous ?

## Exercice 3 - Création d'un composant avec state

### 1 - Initialisation du projet
Plusieurs possibilités :
- Continuer sur le même projet
- Télécharger le projet initialisé depuis le GitHub [Formation React 2025](https://github.com/orgs/Formation-React-2025/repositories) :
  - ```git clone https://github.com/Formation-React-2025/exercice_3.git```

### 2 - Mise à jour de variable
- Dans le package ```./src/components/input/buttons/on-click-button```, créer un composant `OnClickButtonWithState` :
- Le composant est iso au composant `OnClickButton` à la différence qu'il utilise le hook `useState` pour la gestion de sa variable.
- Que constatez-vous ?

### 3 - Création d'un composant avec state
- Dans le package ```./src/features/exercices/pages/exercice-3```, créer le composant ```Exercice3Page```.
- Titre : "Exercice 3 - Création d'un composant avec state"
- Le composant retournera un formulaire avec deux champs de saisie de type ```text``` et un bouton de type ```submit```.
-  Les champs seront ```controlled``` (i.e. leurs valeurs seront gérées au travers d’un « state » React) et ```required```
-  Les libellés des champs seront les suivants :
    - « Nom »
    - « Prénom »
- Le bouton portera la mention « Enregistrer ».

- À la soumission du formulaire, contrôler que les champs obligatoires sont bien renseignés. Si ce n’est pas le cas, afficher les champs en rouge avec le message « Le champ est obligatoire ».

- Dans le fichier ```./src/App.jsx```, appeler le composant.

<u>Notes :</u>
- Afin de ne pas propager l’évènement de validation du formulaire, on pourra utiliser la méthode ```e.preventDefault()```.
- Nous pourrons utiliser du CSS pour gérer les couleurs ou bien utiliser la props `style`

## Exercice 4 - Composants d'input

### 1 - Initialisation du projet
Plusieurs possibilités :
- Continuer sur le même projet
- Télécharger le projet initialisé depuis le GitHub [Formation React 2025](https://github.com/orgs/Formation-React-2025/repositories) :
    - ```git clone https://github.com/Formation-React-2025/exercice_4.git```

### 2 - InputText
- Créer un composant ```InputText``` » dans le package ```./src/components/input/input-text``` ».
- Le composant retourne un ```controlled``` input de type ```text``` dont la valeur est passée en props.
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
- Dans le package ```./src/features/exercices/pages/exercice-4```, créer le composant `Exercice4Page`
- Titre: "Exercice 4 - Composants d'input"
- Le comportement du composant est le même que celui de l’exercice 3 mais doit cette fois-ci utiliser les nouveaux composants ```InputText``` et ```LabelButton```.

### 4 - Conditionnal rendering
- Au clic sur le bouton, afficher en dessous-du formulaire "Le prénom est Jean !!" SSI la valeur du champ "Prénom" vaut "Jean"

### 5 - useEffect
- Mettre en place un useEffect qui affiche en console "Le nom saisit est Dupont !' dès que la valeur du champ "Nom" vaut "Dupont"

## Exercice 5 - Tableau et .map

### 1 - Initialisation du projet
Plusieurs possibilités :
- Continuer sur le même projet
- Télécharger le projet initialisé depuis le GitHub [Formation React 2025](https://github.com/orgs/Formation-React-2025/repositories) :
    - ```git clone https://github.com/Formation-React-2025/exercice_5.git```

### 2 - Construction d'un tableau
#### 2.1 Pré-requis
- Pour gérer différentes opérations sur les dates, nous allons utiliser la librairie ```date-fns```. Pour cela, lancer la commande ```npm install date-fns@4.1.0```
- Télécharger le fichier [Date.utils.js](https://github.com/Formation-React-2025/datas/blob/main/Date.utils.js) dans le package ```./src/utils```
- Télécharger le fichier [users_small.json](https://github.com/Formation-React-2025/datas/blob/main/users_small.json) dans le package ```./src/datas```
- Télécharger le modèle [User.model.js](https://github.com/Formation-React-2025/datas/blob/main/User.model.js) dans le package ```./src/models```.

#### 2.2 Création du composant
##### 2.2.1 Desription
- Dans le package ```./src/features/exercices/pages/exercice-5```, créer le composant ```Exercice5Page```
- Titre: "Exercice 5 - Tableau et .map"
- Le composant doit afficher, dans un tableau, la liste des utilisateurs du fichier ```JSON``` :
  ```
  import usersJon from '../../../datas/users_small.json';
  ```
- Les utilisateurs seront stockés dans un state :
  ```
  const [
    users,
  ] = useState(usersJon.map((u) => new User(u)));
  ```

Les colonnes du tableau sont les suivantes :
- Identifiant
- Civilité (```M.``` ou ```Mlle``` ou ```Mme```)
- Prénom
- Nom
- Âge
- E-mail
- Date de dernière modification

##### 2.2.2 - Initialisation du tableau
- Initialiser le tableau ainsi que les colonnes en utilisant les balise `<table>`, `<thead>`, `<tr>`, et `<th>`
- [table](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/table)
- [thead](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/thead)
- [tr](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/tr)
- [th](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/th)

##### 2.2.3 - Composant ligne
- Créer un composant `UserRow.jsx` qui prend en entrée un user et qui afficher une ligne du tableau en utilisant les balises `<tr>`, `<th>` et `<td>`
- [tr](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/tr)
- [th](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/th) 
- [td](https://developer.mozilla.org/fr/docs/Web/HTML/Reference/Elements/td) 

<u>Notes :</u>
- On pourra définir un fichier de constantes `./src/constants/Civilites.constants.js` pour le mapping des civilités
- On pourra utiliser la méthode `.getAge()` de la classe `User.model.js` pour afficher l'âge
- On pourra utiliser la méthode ```toLocaleDateString``` de  `Date` pour gérer l'affichage de la date de dernière modification
- [toLocaleDateString](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleDateString)

##### 2.2.4 - Corps du tableau
- Rajouter dans le tableau le `<tbody>` et utiliser le `.map` sur les users pour afficher les lignes du tableau (en utilisant le composant `UserRow`)

##### 2.2.5 - .map sur les colonnes
- Créer un fichier `UserColumns.js`
- Dans le fichier, définir un tableau d'objets `USER_COLUMNS` comportant les propriétés ci-dessous et décrivant les colonnes du tableau :

  | Propriété  | Description                                                                                          |
  |------------|------------------------------------------------------------------------------------------------------|
  | `id`       | Identifiant de la colonne.                                                                           | 
  | `title`    | Titre de la colonne                                                                                  |
  | `render`   | Fonction prenant en entrée un user et retournant la valeur de la cellule à afficher pour la colonne  |

  ```
  const USER_COLUMNS = [
    {
      id: 'id',
      title: 'Identifiant',
      render: (u) => u.id,
    },
    ...
  ]
  ```

##### 2.2.6 - HeaderCell.jsx
- Créer un composant `HeaderCell` qui prend en entrée une colonne et qui retourne une header cell du tableau (`<th>`) avec le titre de la colonne.
- Dans `Exercice5Page`, importer le tableau des colonnes
- Dans le header du tableau, boucler sur le tableau des colonnes et appeler le composant `HeaderCell`

##### 2.2.7 - BodyCell.jsx
- Créer un composant `BodyCell` qui prend en entrée une colonne et un user et qui retourne une cellule du tableau (`<td>`) contenant le résultat de la méthode `render` définie dans la colonne
- Ajouter la props `columns` au composant `UserRow.jsx` et boucler sur les colonnes pour appeler le composant `BodyCell`

<u>Notes :</u>
- Afin de ne pas répéter plusieurs fois la déclaration du type de la props `column`, nous pouvons créer le fichier `./src/types/column/ColumnTypes.js` comme suit :
  ```
  import PropTypes from 'prop-types';
  
  const ColumnTypes = PropTypes.shape({
    id: PropTypes.string,
    title: PropTypes.string,
    render: PropTypes.func,
  });
  
  export default ColumnTypes;
  ```

## Exercice 6 - Tableau et tri
Nous allons mettre en place la possibilité de trier les colonnes du tableau.

### 1. SortHeaders.jsx
#### 1.1. Pré-requis
- Télécharger le fichier [SortDirection.constants.js](https://github.com/Formation-React-2025/datas/blob/main/SortDirection.constants.js) dans le package `./src/constants`
- Télécharger le fichier [Sort.types.js](https://github.com/Formation-React-2025/datas/blob/main/Sort.types.js) dans le package `./src/types`
- Télécharger le fichier [SortDescIcon.jsx](https://github.com/Formation-React-2025/datas/blob/main/SortDescIcon.jsx) dans le package `./src/components/icons`
- Télécharger le fichier [SortIncactiveIcon.jsx](https://github.com/Formation-React-2025/datas/blob/main/SortIncactiveIcon.jsx) dans le package `./src/components/icons`

#### 1.2. Création du composant
- Créer un composant ```HeaderCell.jsx``` dont les props sont les suivantes : 
  ```
  HeaderCell.propTypes = {
    column: ColumnTypes.isRequired,
    sort: SortTypes,
    onSortChange: PropTypes.func,
  };
  ```

Le comportement du composant est le suivant :
- Affiche `column.title` (dans une balise `<th>`)
- A droite du titre, afficher une icône :
  - Lorsqu'aucun tri n'est appliqué sur la colonne, afficher `<SortInactiveIcon />`
  - Lorsqu'un tri est appliqué sur la colonne, afficher de façon permanente `<SortDescIcon />`. De plus si le tri est croissant (`ASC`) appliquer une rotation de 180° à l'icône
  - Le contenu du composant est clickable (utiliser une balise `<button>` :
  - Au clic, exécuter la props `onSortChange` avec la nouvelle valeur de tri.
  - La nouvelle valeur de tri se calcule comme suit :
    - Si `sort.order !== column.id`, nouvelle valeur = 
    ```
    {
      order: column.id,
      direction: SortDirection.ASC,
    }
    ```
    - Sinon (`sort.order === column.id`), si `sort.direction === SortDirection.ASC`, nouvelle valeur = 
    ```
    {
      order: column.id,
      direction: SortDirection.DESC,
    }
    ```
    - Sinon nouvelle valeur =
    ```
    {
      order: '',
      direction: '',
    }
    ```

<u>Notes :</u> 
- Nous considérerons qu'un tri est appliqué sur la colonne SSI `sort.order === column.id` et `sort.direction === SortDirectionConstants.ASC || sort.direction === SortDirectionConstants.DESC`
- On pourra utiliser les propriétés [`transform`](https://developer.mozilla.org/fr/docs/Web/CSS/transform) et [`transition`](https://developer.mozilla.org/fr/docs/Web/CSS/transition) pour gérer la rotation et l'animation des icônes
- Pour indiquer que la cellule est cliquable, on utilisera la propriété CSS `cursor: pointer`
- On pourra tester le composant en lui faisant passer différentes props de manière statique

#### 1.3. Utilisation
- Reprendre le composant de l'exercice 5 (copier / coller les composants dans le package `./src/features/exercices/pages/exercice-6`.)
- Le composant devra maintenant gérer les variables de tri dans un state et utiliser le composant HeaderCell.jsx pour afficher les cellules du header du tableau
- Les lignes du tableau devront être affichées selon le tri du state du composant (attention à ne pas modifier la structure du tableau)

## Exercice 7 - Tableau et pagination
Nous allons mettre en place la pagination sur le tableau de l'exercice 6

- Télécharger le fichier [users.json](https://github.com/Formation-React-2025/datas/blob/main/users.json) dans le répertoire `./src/datas`
- Télécharger les fichiers du répertoire [pagination](https://github.com/Formation-React-2025/datas/tree/main/pagination) dans le répertoire `./src/components/pagination`
- Copier / Coller les composants de l'exercice précédent dans le package `./src/features/exercices/pages/exercice-7`
- Modifier les users chargés par le contenu du nouveau fichier `JSON`
- Le composant affichant le tableau doit maintenant gérer dans son state la page du tableau à afficher
- Dans le footer du tableau, faire appel au composant `./src/components/pagination/Pagination.jsx` en footer du tableau
- Utiliser le composant pour mettre à jour les lignes du tableau affichées en fonction de la page sélectionnée (attention à ne pas modifier la structure du tableau)


## Exercice 8 - Exercice 8 - react-query : Récupération des users via API
- Lancer la commande `npm install @tanstack/react-query@5.81.5`
- Lancer la commande `npm axios@1.10.0`
- Télécharger le projet [api_backend](https://github.com/Formation-React-2025/api_backend) `git clone https://github.com/Formation-React-2025/api_backend.git`
- Lancer l'API : dans le répertoire `api_backend` lancer les commandes `npm install` puis `npm start`
  - Reprendre l'exercice précédent et charger les users en appellant `GET http://localhost:8080/users`

## Exercice 9 - react-query : Formulaire de création d'un utilisateur
- Créer un composant `CreateUser.jsx`
- Le composant affiche un formulaire permettant de créer un nouvel utilisateur selon les règles précisées par l'[API](https://github.com/Formation-React-2025/api_backend)
- À la soumission du formulaire, contrôler la validité des champs
- Si tous les champs sont OK envoyer la requête de création `POST http://localhost:8080/users`, sinon mettre les champs en erreur en rouge
- En cas d'erreur lors de l'ennvoi de la requête (`response.status !== 201`, afficher le message d'erreur sous le formulaire

## Exercice 10 - react-router-dom : Routage et Barre de navigation
### 1 - Installation
- Lancer la commande `npm install react-router-dom@7.6.3`

### 2 - Création de routes et redirection
- Pour chaque exercice i dans {1, ..., 9}, créer un path `exercice-i` qui affiche l'Exercice n° i
- Tout path non reconnu redirige vers /exercice-1

### 3 - Créer une bar de navigation
- Créer le composant `./src/components/nav/AppNavBar.jsx`
- Le composant affiche un menu vertical avec des liens pour chaque exercice
- Nous pourrons utiliser le composant `NavLink` afin de mettre en évidence le menu couramment sélectionné
- Appeler AppNavBar dans ExerciceLayout

## Exercice 11 - Page infos utilisateur (routage + nested routes + react query GET /users/XXX et PATCH /users/XXX)

### 1 - UserView.jsx
Créer composant UserView avec le path /users
Tout path non reconnu redirige vers /users
Le composant UserView charge les users du fichier JSON et appelle le composant userTable
Ajouter un lien vers "/users" dans la nav bar

### 2 - UserInfos.jsx
Créer composant UserInfos affichant les informations utilisateur avec le path /users/XXX/infos
/users/XXX/* => redirection vers page /users/XXX/infos
Ajouter une nouvelle colonne dans le tableau pour rediriger vers /users/XXX/infos

### 3 - CreateUser.jsx
Dans le composant UserView, ajouter un lien redirigeant vers /users/create qui affiche CreateUsers.jsx

### 4 - UpdateUser.jsx
Créer le composant UpdateUsers.jsx sur le path /users/XXX/update qui permet de modifier un utilisateur
Ajouter une colonne dans le tableau pour rediriger vers la page de modification
Ajouter un lien dans le composant UserInfos pour rediriger vers la page de modification

## Exercice 12 - Reducer
### 1 - Installations
- Lancer la commande `npm install react-redux@9.2.0`
- Lancer la commande `npm install @reduxjs/toolkit@2.8.2`

### 2 - Initialiser un store
- Dans le package `./src/redux` initialiser le fichier `store.js` :
  ```
  import { configureStore, } from '@reduxjs/toolkit'
  
  export default configureStore({
    reducer: {},
  });
  
  ```

- Créer un composant Notification dont les variables seront récupérer depuis un store `reducer` (création de `NotificationSlice.js` en utilisant `createSlice` de `@reduxjs/toolkit`
- Le composant ne sera appelé qu'une seule fois à la racine du projet

Les variables reçus de ce store sont les suivantes : 

| Variable  | Description                                                                                                 | type       | valeurs possibles                             | Valeur par défaut |
|-----------|-------------------------------------------------------------------------------------------------------------|------------|-----------------------------------------------|-------------------|
| `status`  | Décrit le statut de la notification. <br/> La couleur de la notification sera adaptée en fonction du status | `string`   | `INFO`, `SUCCESS`, `WARNING`, `ERROR` ou `""` | `""`              | 
| `message` | Message à afficher dans la notification                                                                     | `string`   |                                               | `""`              |
| `show`    | Décrit si oui ou non la notification est affichée                                                           | `boolean`  |                                               | `false`           |

- Trois fonctions seront exposées depuis le store :
- `show` qui prend en paramètre le message et le status à afficher et qui déclenche l'affichage de la notification
- `hide` qui déclence le masquage de la notification
- `reset` qui reset le status et le message de la notification

### 3 - Afficher les notifications
- Dans le composant UserView, dispatcher une notification d'erreur si le user n'est pas trouvé
- Dans le composant UsersView, dispatcher une notification d'erreur si les users ne sont pas trouvé
- Dans les composant CreateUser et UpdateUser afficher :
  - Une notification d'erreur si la création (resp. la maj) est en erreur
  - Une notification de succès si la création (resp. la maj) est en succès

<u>Note :</u>
- La notification sera affichée en haut de l'écran de façon centrée et disparaîtra au bout de quelques seconcdes (5s)
- Une animation fera descendre (puis remonter) à son affichage (resp. à son masquage)


## Exercice 13 - Filtres &  react-router
- Nous allons mettre en place une gestion d'affichage des lignes du tableau via query params.
- Ainsi, la pagination et le tri sur les colonnes sera gérée en fonction de l'URL
- Nous mettrons en place des filtres supplémentaires pour filtrer les lignes du tableau

### 1 - Pagination.jsx
- Modifier Pagination.jsx et UserTable.jsx pour gérer la pagination en query param grâce au hookt [useSearchParams](https://reactrouter.com/api/hooks/useSearchParams);
- Les query params sont les suivants : `pageSize` et `pageNumber`

### 2 - Tri.jsx
- Utiliser [useSearchParams](https://reactrouter.com/api/hooks/useSearchParams) pour mettre à jour l'URL lorsque le tri change
- Modifier UserTable pour prendre en compte les paramètres de tri dans l'URL
- Les query params sont les suivants : `sortOrder` et `sortDirection`

### 3 - Filtres
- Créer un composant UserFiltres.jsx, affichant un formaulaire permettant de filtrer chacune des colonnes du tableau (1 champ par colonne)
- Les données saisies dans le formulaire seront gérées grâcee à [useSearchParams](https://reactrouter.com/api/hooks/useSearchParams)
- Les query params sont les suivants :
  - `identifiant`
  - `civilite`
  - `prenom`
  - `nom`
  - `ageMin`
  - `ageMax`
  - `dateModificationMin`
  - `dateModificationMax`

<u>Note :</u> Le tri et la pagination doivent être appliqué une fois les users filtrés.

## Exercice 14 - Utiliser react-router pour gérer les forrmulaires "uncontrolled"
