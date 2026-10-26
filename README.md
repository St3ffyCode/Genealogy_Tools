# Outils de généalogie

Petits outils pour travailler à partir d'un fichier **GEDCOM**. Chaque outil est une **page web autonome** : un seul fichier HTML, rien à installer, aucune donnée envoyée sur Internet.

## Les outils

| Outil | À quoi il sert | Fichier à télécharger | Mode d'emploi |
|---|---|---|---|
| **Actes à rechercher** | Liste les naissances, baptêmes, mariages, décès… sans source, classés par département et par pays, avec suivi d'avancement, sous forme de classeur Excel | [`Actes_a_rechercher.html`](Actes_a_rechercher/Actes_a_rechercher.html) | [README](Actes_a_rechercher/README.md) |
| **Recherche d'indices GEDCOM** | Retrouve les événements qui correspondent à un indice (nom, rue, lieu, période) trouvé dans un article, une annonce ou un acte | [`Recherche_indices_GEDCOM.html`](Recherche_indices_GEDCOM/Recherche_indices_GEDCOM.html) | [README](Recherche_indices_GEDCOM/README.md) |

## Utiliser un outil

Les outils ne s'utilisent pas depuis GitHub : GitHub n'en affiche que le code. Il faut **télécharger le fichier HTML** puis l'ouvrir chez vous.

1. Cliquez sur le nom de l'outil dans le tableau ci-dessus.
2. En haut à droite de la zone qui s'ouvre, cliquez sur l'icône de **téléchargement** (une flèche qui pointe vers le bas, infobulle « Download raw file »).
3. Ouvrez le fichier téléchargé par un double-clic : il s'ouvre dans votre navigateur.

Le détail des étapes, avec une méthode pour télécharger tout le dépôt, se trouve dans le README de chaque outil.

## Confidentialité

Un GEDCOM contient des données personnelles, parfois sur des personnes vivantes. **Ne le publiez pas** dans un dépôt public ni ailleurs. Le fichier `.gitignore` exclut les fichiers `.ged`, `.gedcom`, les classeurs produits par *Actes à rechercher* et les exports CSV de *Recherche d'indices GEDCOM*.

## Licence

Licence **MIT** (voir le fichier `LICENSE`). Les composants tiers embarqués dans *Actes à rechercher* sont listés dans son README.

## Auteur

[St3ffyCode](https://github.com/St3ffyCode)
