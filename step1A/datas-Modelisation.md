# Etape 1A : Choix des données et structure

- ## structure des données choisies
  
  - Utilisation de JSON pour représenter les données
  
- ## Modèle de données pour les tâches
  
- ### Structure JSON

- #### Chaque tâche est un objet avec les paires propriétés/valeurs suivantes:

  -  id de la tâche (integer, unique)
  -  libellé de la tâche (string)
  -  date de création (string, format ISO 8601)
  -  date de modification (string, format ISO 8601)
  -  date de complétion (string, format ISO 8601, nullable)
  -  compteur de temps passé (integer, en minutes)
  -  description (string, nullable)
  -  assignation (string, nullable)
  -  documentation (array de strings, nullable)
  -  fichiers joints (array de strings, nullable)
  -  to do list associée (Type de la valeur : Array ([])
  
    - ##### Contenu de l'Array : Un Objet unique
   
       - ###### Propriétés de l'Objet :
  
          - "ToDoA" : Array d'Objets (chaque objet a les propriétés idToDoA, subTask, commentaire).  
          - "ToDoB" : Array d'Objets (chaque objet a les propriétés idToDoB, subTask, commentaire).)

- #### Justification des choix

  - Utilisation de types simples pour faciliter la manipulation des données en JavaScript.
  - Inclusion de dates pour le suivi de l'historique des tâches.
  - Ajout d'un compteur de temps pour mesurer la productivité.
  - Utilisation de tableaux pour les éléments pouvant avoir plusieurs valeurs (documentation, fichiers joints, to do list).
  - Utilisation de valeurs optionnelles pouvant être nulles pour les propriétés non obligatoires.
  - Structure flexible pour permettre des extensions futures.
  - Format JSON largement supporté et facile à lire.
  - Facilité d'intégration avec des API RESTful.
  - Compatibilité avec les frameworks front-end modernes.
  - Simplicité pour le stockage et la récupération des données.
  - Facilité de validation des données.
  - Support pour les opérations CRUD (Create, Read, Update, Delete).
  - Adaptabilité aux besoins changeants du projet.

- ### Exemple de structure JSON pour une tâche

```json
{
  "id": 1,
  "libellé": "Exemple de tâche",
  "date_de_création": "2023-10-01T10:00:00Z",
  "date_de_modification": "2023-10-01T10:00:00Z",
  "date_de_complétion": null,
  "compteur_de_temps_passé": 0,
  "description": "Description détaillée de la tâche.",
  "assignation": "Utilisateur A",
  "documentation": ["http://lien-vers-doc1.com", "http://lien-vers-doc2.com"],
  "fichiers_joints": ["fichier1.pdf", "image2.png"],
  "to_do_list_associee": [
      {
        "ToDoA": [
          {
            "idToDoA"    : "uniqueId",
            "subTask"    : "Sous tâche",
            "commentaire": "description etc..."
          }
        ],
        "ToDoB": [
          {
            "idToDoB"    : "uniqueId",
            "subTask"    : "Sous tâche",
            "commentaire": "description etc..."
          }
        ]
      }
    ] 
}
```

- ### Exemple de structure JSON pour un ensemble de tâches

```json
[
  {
    "id": 1,
    "libelle": "TP Histoire de l'art: Période Baroque",
    "date_de_creation": "2023-10-01T10:00:00Z",
    "date_de_modification": "2023-10-01T10:00:00Z",
    "date_de_completion": null,
    "compteur_de_temps_passe(mn)": 120,
    "description": "Préparer un résumé des précurseurs du Baroque en France et en Europe.",
    "assignation": "Justine",
    "documentation": ["http://lien-vers-doc1.com"],
    "fichiers_joints": ["fichier1.pdf"],
    "to_do_list_associee": [
      {
        "ToDoA": [
          {
            "idToDoA"    : "A1",
            "subTask"    : "France",
            "commentaire": "Période d'ouverture"
          }
        ],
        "ToDoB": [
          {
            "idToDoB"    : "B1",
            "subTask"    : "France",
            "commentaire": "Période d'ouverture"
          }
        ]
      }
    ]
  },
  {
    "id": 2,
    "libelle": "Colorimétrie",
    "date_de_creation": "2023-10-01T10:00:00Z",
    "date_de_modification": "2023-10-01T10:00:00Z",
    "date_de_completion": null,
    "compteur_de_temps_passe(mn)": 120,
    "description": "Comprendre les codes héxadécimaux et leur nomenclature.",
    "assignation": "Justine",
    "documentation": ["http://lien-vers-doc2.com"],
    "fichiers_joints": ["fichier2.pdf"],
    "to_do_list_associee": [
      {
        "ToDoA": [
          {
            "idToDoA"    : "A1",
            "subTask"    : "Comparaison",
            "commentaire": "RGB et Hexadécimal"
          }
        ],
        "ToDoB": [
          {
            "idToDoB"    : "B1",
            "subTask"    : "Comparaison",
            "commentaire": "HSL et Héxadécimal"
          }
        ]
      }
    ]
  }
]


```
