# Recherche d'indices GEDCOM

Retrouve, dans un arbre généalogique, les événements qui correspondent à un indice : un nom, une rue, un lieu, une période.

Vous avez trouvé un article de journal, une annonce ou un acte avec un nom, une adresse et une date, et vous voulez savoir à quelle personne de votre **GEDCOM** cela peut correspondre. Une recherche dans le Bloc-notes trouve la ligne `116 rue de Strasbourg`, mais pas à qui elle appartient. L'outil liste les événements concernés, avec le type d'événement, les personnes, les sources et les médias associés.

C'est un **fichier HTML unique** : rien à installer, rien à configurer. Tout se passe sur votre ordinateur, dans le navigateur (voir [Confidentialité](#confidentialité)).

## Sommaire

- [Récupérer l'outil sur GitHub](#récupérer-loutil-sur-github)
- [Ce que fait l'outil](#ce-que-fait-loutil)
- [Utilisation](#utilisation)
- [Saisir les mots-clés](#saisir-les-mots-clés)
- [Filtres](#filtres)
- [Lire un résultat](#lire-un-résultat)
- [Règles de lecture du GEDCOM](#règles-de-lecture-du-gedcom)
- [Export CSV](#export-csv)
- [Confidentialité](#confidentialité)
- [Compatibilité et limites](#compatibilité-et-limites)
- [Contenu du dépôt](#contenu-du-dépôt)
- [Licence](#licence)
- [Auteur](#auteur)

## Récupérer l'outil sur GitHub

GitHub est le site où se trouve l'outil. Il suffit de récupérer **un seul fichier**, `Recherche_indices_GEDCOM.html`, et de le garder sur votre ordinateur. Le fichier se trouve dans le dossier `Recherche_indices_GEDCOM` du dépôt : <https://github.com/St3ffyCode/Genealogy_Actes_a_rechercher/tree/main/Recherche_indices_GEDCOM>

**Méthode 1 : télécharger le fichier seul (la plus simple)**

1. Ouvrez l'adresse ci-dessus dans votre navigateur.
2. Dans la liste des fichiers, cliquez sur `Recherche_indices_GEDCOM.html`. (Si vous êtes à la racine du dépôt, ouvrez d'abord le dossier `Recherche_indices_GEDCOM`.)
3. En haut à droite de la zone qui s'ouvre, cliquez sur l'icône de **téléchargement** (une flèche qui pointe vers le bas, infobulle « Download raw file »).
4. Le fichier arrive dans votre dossier **Téléchargements** (le navigateur peut vous demander où l'enregistrer).
5. Déplacez-le si vous le souhaitez dans un dossier facile à retrouver, par exemple « Documents ».

**Méthode 2 : télécharger tout le dépôt**

1. Ouvrez la page d'accueil du dépôt : <https://github.com/St3ffyCode/Genealogy_Actes_a_rechercher>
2. Cliquez sur le bouton vert **Code**, puis sur **Download ZIP**.
3. Le fichier `.zip` arrive dans « Téléchargements ». Faites un clic droit dessus, puis **Extraire tout** (Windows) ou double-cliquez dessus (Mac).
4. Dans le dossier obtenu, le fichier à utiliser est `Recherche_indices_GEDCOM/Recherche_indices_GEDCOM.html`. Les autres outils du dépôt sont dans leurs propres dossiers.

**Ouvrir l'outil**

- Faites un **double-clic** sur `Recherche_indices_GEDCOM.html`. Il s'ouvre dans votre navigateur.
- Si le fichier s'ouvre dans un éditeur de texte ou ne s'ouvre pas : clic droit sur le fichier, **Ouvrir avec**, puis choisissez votre navigateur (Chrome, Firefox, Edge…).
- Aucune connexion à Internet n'est nécessaire pour l'utiliser.

**Récupérer une version plus récente :** refaites la méthode 1 et remplacez l'ancien fichier par le nouveau.

> Le texte de ces étapes décrit le site GitHub tel qu'il est au moment de la rédaction. Si les boutons ont changé de place ou de nom, cherchez l'icône de téléchargement ou le bouton vert « Code ».

## Ce que fait l'outil

1. Lit un fichier GEDCOM (encodage détecté automatiquement).
2. Construit la liste de tous les événements : naissances, baptêmes, mariages, décès, inhumations, professions, résidences, recensements, événements personnalisés, etc.
3. Cherche vos mots-clés dans le lieu, le nom de la personne, le nom de ses proches, la date, le libellé et les notes, et dans les sources et fichiers médias.
4. Affiche pour chaque événement correspondant : le type, la date, le lieu complet, les personnes concernées, la présence ou non d'une source, et les médias rattachés.
5. Indique, pour chaque mot-clé, **où il a été trouvé**, pour juger de la pertinence d'un résultat.

## Utilisation

**Prérequis :** un navigateur récent. Rien à installer.

1. Ouvrez `Recherche_indices_GEDCOM.html` par un double-clic, ou glissez-le dans le navigateur.
2. Déposez votre fichier `.ged` sur la zone prévue, ou cliquez dessus pour le choisir. Le nombre d'individus, de familles, d'événements, de sources et de médias s'affiche.
3. Saisissez un ou plusieurs mots-clés. La recherche se lance en cours de frappe, ou avec Entrée ou le bouton *Rechercher*.
4. Affinez avec les filtres, puis parcourez les résultats. Ils s'affichent par pages de 60 ; un bouton affiche la suite.

Pour changer de fichier, déposez-en un autre sur la même zone.

## Saisir les mots-clés

Séparez les mots-clés par une **virgule**, un point-virgule ou un retour à la ligne :

```
Dupont, rue de la gare
```

- Chaque mot-clé est cherché **tel quel**, comme une expression : `rue de la gare` ne trouve que ces trois mots à la suite.
- Les **accents** et les **majuscules** sont ignorés. Les tirets, apostrophes, points et virgules sont traités comme des espaces, donc `meurthe et moselle` trouve `Meurthe-et-Moselle`.
- Un mot-clé précédé de `-` **exclut** les événements qui le contiennent : `rue de la gare, -12 rue`.
- **Association** : *ET* (par défaut) exige que tous les mots-clés soient trouvés, *OU* se contente d'un seul.
- Option **Un espace sépare deux mots-clés** : chaque mot devient alors un mot-clé indépendant.

Sans mot-clé, tous les événements qui passent les filtres sont listés.

### Variantes phonétiques

L'option est cochée par défaut. Elle rapproche des graphies voisines en appliquant des règles simples aux deux côtés de la comparaison :

| Règle | Exemple |
|---|---|
| `w` devient `v` | `Wagner` / `Vagner` |
| `oe`, `ae`, `ue` et `ö`, `ä`, `ü` sont ramenés à `o`, `a`, `u` | `Müller` / `Muller` / `Mueller` |
| `ph` devient `f`, `ck` devient `k`, `th` et `dt` deviennent `t` | `Philipp` / `Filip` |
| `y` devient `i`, `ai` devient `ei` | `Meyer` / `Meier` / `Mayer` |
| Les lettres doublées sont réduites | `Schaeffer` / `Schaefer` |

Ces règles ont été pensées pour des noms alsaciens et allemands. Elles peuvent manquer des rapprochements (d'autres origines, autres graphies) ou en ajouter de faux : décochez l'option si le résultat est trop bruité. Le surlignage en mode phonétique se fait mot par mot.

### Où chercher

Six zones se cochent séparément :

| Zone | Contenu cherché |
|---|---|
| Lieu / adresse | Le lieu de l'événement et son adresse |
| Nom de la personne | Les noms et prénoms de la personne, avec leurs variantes (surnom, nom marital) |
| Noms des proches | Parents, conjoints, enfants (pour un mariage : enfants et parents des deux époux) |
| Date | Le texte de la date |
| Libellé / cause / notes | Type d'événement, valeur, cause, organisme, âge, notes |
| Sources & fichiers médias | Titres, pages, textes et notes des sources, noms des fichiers médias |

Pour retrouver une rue sans être gêné par un homonyme, ne cochez que *Lieu / adresse*.

## Filtres

- **Années** : de / à. Un événement est retenu si sa période croise l'intervalle demandé. Sont lues les dates `12 MAR 1890`, `MAR 1890`, `1890`, avec les préfixes `ABT`, `CAL`, `EST`, `BEF`, `AFT`, et les plages `BET … AND …` et `FROM … TO …` (les formes françaises *avant* et *après* aussi). *Inclure les événements sans date* est coché par défaut.
- **Types d'événements** : naissance, baptême, mariage (avec bans, contrat, fiançailles), décès, inhumation ou crémation, divorce, autres événements, et notes ou sources rattachées à une fiche. Le nombre d'événements de chaque type est affiché.
- **Source** : toutes, avec source, sans source.
- **Média** : tous, avec média, sans média.
- **Tri** : pertinence, date croissante ou décroissante, type, lieu, nom. La pertinence compte davantage un mot-clé trouvé dans le lieu ou le nom que dans un proche ou une source.

Le bouton *Réinitialiser* remet tous les réglages à zéro.

## Lire un résultat

Chaque événement est une carte :

- **Type** (Naissance, Baptême, Mariage, Décès…), **date** et **lieu complet**. Les mots-clés sont surlignés.
- **Source** : ✔ avec le nombre de sources, ou ✖ *Sans source*.
- **Médias** : le nombre de fichiers et leurs extensions (JPG, PNG, PDF…).
- **Personnes** : nom, années de vie, identifiant GEDCOM. Pour un mariage, l'époux et l'épouse.
- **Proches** : parents, conjoints et enfants, pour aider à reconnaître la bonne personne.
- **Détails** : type, valeur, cause ou précision, organisme, âge, adresse, coordonnées, notes.
- **Sources** : titre, page, auteur, texte, fiabilité (`QUAY` de 0 à 3), identifiant de la source et ses médias.
- **Correspondances** : pour chaque mot-clé, la ou les zones où il a été trouvé (lieu, nom, proche…).
- **Fiche complète** : un volet dépliable par personne, avec ses parents, ses unions et tous ses événements (date, lieu, source oui ou non, médias).

En tête de liste, un résumé donne le nombre d'événements et de personnes, la répartition par type, et le nombre d'événements avec source et avec média.

## Règles de lecture du GEDCOM

**Événements lus.** Les balises d'événement usuelles (`BIRT`, `CHR`, `BAPM`, `DEAT`, `BURI`, `CREM`, `MARR`, `MARB`, `MARC`, `DIV`, `OCCU`, `RESI`, `CENS`, `EVEN`, `FACT`, etc.) sont reconnues. Toute autre balise qui porte une date ou un lieu est lue comme « autre événement ». Un événement `EVEN` ou `FACT` prend le libellé de son `TYPE`. Les événements de famille (mariage, divorce…) sont rattachés aux deux conjoints.

**Source d'un événement.** Un événement est dit *avec source* s'il a au moins une balise `SOUR` sous lui-même. Une source posée sur la personne ou sur la famille n'est pas comptée comme source de l'événement ; elle apparaît dans un événement à part, de type *Notes / sources de la fiche*, avec les notes et médias posés au niveau de la fiche.

**Médias.** Sont lus les objets `OBJE`, qu'ils soient posés sous l'événement, sous une citation de source ou dans l'enregistrement de la source, qu'ils soient en ligne ou par référence (`@O1@`). Le nom du fichier vient de la balise `FILE`. L'outil n'ouvre pas les fichiers et ne vérifie pas qu'ils existent : il ne fait que lister ce que le GEDCOM déclare.

**Lieux.** Le lieu est affiché et cherché tel qu'il est écrit dans le GEDCOM, de la forme `Commune, Code postal, Département, Région, Pays, Lieu-dit ou rue`. Aucune interprétation n'est faite : la recherche porte sur le texte.

**Noms.** `Prénom /NOM/` est lu, ainsi que `GIVN`, `SURN`, `NICK` et `_MARNM`. Les noms sont affichés sous la forme `NOM Prénom`.

**Encodage.** UTF-8, UTF-16 (avec ou sans marque d'ordre des octets) et Windows-1252 (ANSI) sont lus.

## Export CSV

Le bouton *Export CSV* enregistre les résultats courants dans `recherche_indices.csv` (séparateur `;`, UTF-8 avec BOM, lisible dans Excel) : type, libellé, date, lieu, personnes, présence de source, sources, fichiers médias, détails, notes et correspondances.

## Confidentialité

- Le fichier est lu dans votre navigateur. Le code ne fait aucune requête réseau et ne charge aucune ressource externe (ni bibliothèque, ni police). Il n'utilise pas non plus le stockage du navigateur : rien n'est mémorisé d'une session à l'autre.
- Un GEDCOM contient des données personnelles, parfois sur des personnes vivantes. **Ne le publiez pas** dans un dépôt public ni ailleurs. Le fichier `.gitignore` fourni exclut `.ged`, `.gedcom` et les exports CSV.

## Compatibilité et limites

- L'outil a été testé sur un petit GEDCOM d'exemple écrit pour l'occasion, avec des tests automatiques du moteur de recherche et une simulation de navigateur sans erreur. Il n'a pas été essayé sur des fichiers réels volumineux ni dans les navigateurs eux-mêmes : les performances sur un très gros arbre et le rendu dans Firefox, Safari ou Edge ne sont pas vérifiés.
- Le format ANSEL (ancien encodage GEDCOM) n'est pas géré : les accents peuvent être mal restitués.
- Les variantes phonétiques sont des règles simples (voir plus haut), pas un dictionnaire de noms.
- Les fichiers médias ne sont ni ouverts ni vérifiés.
- L'export se fait en CSV, pas en Excel.
- Les dates en calendrier républicain ou dans une forme non reconnue sont conservées telles quelles et traitées comme sans date pour le filtre d'années.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `Recherche_indices_GEDCOM.html` | L'outil, autonome |
| `README.md` | Ce fichier |

À la racine du dépôt, commun à tous les outils : `LICENSE` (licence MIT) et `.gitignore` (exclut les données personnelles : fichiers `.ged`, `.gedcom`, classeurs et exports CSV, si vous utilisez git).

## Licence

Ce projet est distribué sous licence **MIT** (voir le fichier `LICENSE` à la racine du dépôt) : vous pouvez l'utiliser, le copier, le modifier et le partager librement, à condition de conserver le nom de l'auteur et la mention de licence. Il est fourni tel quel, sans garantie.

## Auteur

[St3ffyCode](https://github.com/St3ffyCode)
