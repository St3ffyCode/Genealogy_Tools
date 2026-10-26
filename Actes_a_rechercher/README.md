# Actes à rechercher

Prépare la recherche dans les registres des Archives départementales à partir d'un arbre généalogique.

L'outil lit un fichier **GEDCOM** et dresse la liste des **naissances, baptêmes, mariages, divorces, décès, inhumations et sépultures qui n'ont pas de source**. Cette liste est classée par département et par pays, avec un suivi d'avancement, et produite sous forme de classeur Excel.

Tout se passe sur votre ordinateur : aucune donnée n'est envoyée sur Internet (voir [Confidentialité](#confidentialité)).

L'outil est une **page web** qui s'ouvre dans votre navigateur (Chrome, Firefox, Edge, Safari). Il n'y a **rien à installer**.

## Sommaire

- [Récupérer l'outil sur GitHub](#récupérer-loutil-sur-github)
- [Ce que fait l'outil](#ce-que-fait-loutil)
- [Utiliser la page web](#utiliser-la-page-web)
- [Le classeur Excel produit](#le-classeur-excel-produit)
- [Mettre à jour un classeur existant](#mettre-à-jour-un-classeur-existant)
- [Le nom de fichier proposé](#le-nom-de-fichier-proposé)
- [Règles d'extraction](#règles-dextraction)
- [Confidentialité](#confidentialité)
- [Compatibilité et limites](#compatibilité-et-limites)
- [Contenu du dépôt](#contenu-du-dépôt)
- [Composants tiers](#composants-tiers)
- [Licence](#licence)

## Récupérer l'outil sur GitHub

GitHub est le site où se trouve l'outil. Il suffit de récupérer **un seul fichier**, `Actes_a_rechercher.html`, et de le garder sur votre ordinateur. Le fichier se trouve dans le dossier `Actes_a_rechercher` du dépôt : <https://github.com/St3ffyCode/Genealogy_Tools/tree/main/Actes_a_rechercher>

**Méthode 1 : télécharger le fichier seul (la plus simple)**

1. Ouvrez l'adresse ci-dessus dans votre navigateur.
2. Dans la liste des fichiers, cliquez sur `Actes_a_rechercher.html`. (Si vous êtes à la racine du dépôt, ouvrez d'abord le dossier `Actes_a_rechercher`.)
3. En haut à droite de la zone qui s'ouvre, cliquez sur l'icône de **téléchargement** (une flèche qui pointe vers le bas, infobulle « Download raw file »).
4. Le fichier arrive dans votre dossier **Téléchargements** (le navigateur peut vous demander où l'enregistrer).
5. Déplacez-le si vous le souhaitez dans un dossier facile à retrouver, par exemple « Documents ».

**Méthode 2 : télécharger tout le dépôt**

1. Ouvrez la page d'accueil du dépôt : <https://github.com/St3ffyCode/Genealogy_Tools>
2. Cliquez sur le bouton vert **Code**, puis sur **Download ZIP**.
3. Le fichier `.zip` arrive dans « Téléchargements ». Faites un clic droit dessus, puis **Extraire tout** (Windows) ou double-cliquez dessus (Mac).
4. Dans le dossier obtenu, le fichier à utiliser est `Actes_a_rechercher/Actes_a_rechercher.html`. Les autres outils du dépôt sont dans leurs propres dossiers.

**Ouvrir l'outil**

- Faites un **double-clic** sur `Actes_a_rechercher.html`. Il s'ouvre dans votre navigateur.
- Si le fichier s'ouvre dans un éditeur de texte ou ne s'ouvre pas : clic droit sur le fichier, **Ouvrir avec**, puis choisissez votre navigateur (Chrome, Firefox, Edge…).
- Aucune connexion à Internet n'est nécessaire pour l'utiliser.

**Récupérer une version plus récente :** refaites la méthode 1 et remplacez l'ancien fichier par le nouveau. Vos classeurs Excel déjà enregistrés ne sont pas concernés.

> Le texte de ces étapes décrit le site GitHub tel qu'il est au moment de la rédaction. Si les boutons ont changé de place ou de nom, cherchez l'icône de téléchargement ou le bouton vert « Code ».

## Ce que fait l'outil

1. Lit le GEDCOM (encodage détecté automatiquement).
2. Retient chaque événement qui a **une date ou un lieu, mais aucune source**.
3. Range les événements par **département** (France) et par **pays** (autres pays).
4. Propose pour chaque événement un **nom de fichier** (par exemple `1890_03_12 Soultz N DUPONT Jean_Pierre`) pour classer les vues d'actes que vous téléchargerez.
5. Fournit un **suivi** : chaque ligne a un statut (*À rechercher*, *En cours*, *Trouvé*, *Introuvable*, *Registre non présent*) et une note. La page de suivi du classeur calcule l'avancement par département et par pays.
6. Permet de **mettre à jour** le classeur quand l'arbre évolue, sans perdre les statuts et les notes.

## Utiliser la page web

**Prérequis :** un navigateur récent. Rien à installer. Vous avez besoin d'un fichier **GEDCOM** (extension `.ged`) : c'est le fichier que votre logiciel de généalogie produit avec la fonction « Exporter » (ou « Enregistrer sous » au format GEDCOM). Le nom exact de cette fonction dépend du logiciel.

1. Ouvrez `Actes_a_rechercher.html` par un double-clic (voir [Récupérer l'outil sur GitHub](#récupérer-loutil-sur-github)).
2. **Déposer** votre fichier `.ged` : faites-le glisser depuis votre dossier jusque sur la feuille à carreaux (maintenez le bouton de la souris enfoncé pendant le déplacement, puis relâchez). Ou cliquez sur *Choisir un fichier* et sélectionnez-le dans la fenêtre qui s'ouvre.
3. La feuille affiche les statistiques : nombre d'événements sans source, répartition, avancement, points à vérifier.
4. L'onglet **Vue d'ensemble** liste tous les départements et pays avec leurs compteurs. Un clic sur un onglet l'ouvre dans un nouvel onglet de la page.
5. Dans un onglet de département ou de pays :
   - la liste est triée par date (cliquez sur un en-tête pour changer le tri) ;
   - les boutons **Tous / Naissance / Baptême / …** filtrent par type d'événement, et la liste *Statut* filtre par avancement ;
   - une ligne montre la date, l'événement, la ou les personnes (l'époux et l'épouse pour un mariage ou un divorce), la commune, le statut et la note ;
   - un clic sur une ligne déroule la **fiche complète**, avec les mêmes champs que le classeur Excel ;
   - le statut et la note se modifient directement dans la liste.
6. **Télécharger le classeur Excel à jour** exporte le tout, avec vos statuts et vos notes. Un indicateur « Modifications non exportées » s'affiche tant que vous n'avez pas exporté, et le navigateur vous prévient si vous fermez la page avant.

Deux boutons à droite du titre ouvrent des fenêtres :

- **Mettre à jour un classeur** : dépôt de l'ancien classeur Excel, par glisser-déposer ou par le bouton (voir [Mettre à jour un classeur existant](#mettre-à-jour-un-classeur-existant)). Une pastille avec son nom s'affiche sur le bouton et dans la feuille à carreaux tant qu'il est repris ; sa croix le retire.
- **Nom de fichier** : réglage des modèles de nom (voir [Le nom de fichier proposé](#le-nom-de-fichier-proposé)). Le bouton porte la pastille « modifié » quand les réglages ne sont plus ceux d'origine.

Les réglages du nom de fichier sont enregistrés par le navigateur. Ils ne suivent pas d'un navigateur ou d'un ordinateur à l'autre, et sont perdus si vous effacez les données du navigateur.

> Le fichier HTML pèse environ 1,3 Mo : il embarque la bibliothèque qui écrit les fichiers Excel et deux polices, pour fonctionner sans connexion. Le code de l'application se trouve dans la balise `<script id="app">`.

## Le classeur Excel produit

| Feuille | Contenu |
|---|---|
| `Suivi` | Page de garde, sommaire avec liens vers chaque feuille, compteurs par type d'événement, Trouvé / Introuvable / Registre non présent / Restants, avancement en pourcentage (formules) |
| `68 - Haut-Rhin`, `15 - Cantal`… | Une feuille par département français, triées par numéro |
| `Allemagne`, `Suisse`… | Une feuille par pays étranger |
| `France - dépt inconnu` | Lieux français dont le département n'a pas pu être déterminé |
| `Sans lieu` | Événements qui ont une date mais aucun lieu |
| `Non classé` | Lieux dont ni le pays ni le département n'ont pu être déterminés |
| `Sortis` | Lignes avec statut ou note de l'ancien classeur qui ne sont plus dans la liste (voir plus bas) |

**Colonnes de chaque feuille :** Date, Année, Événement, Pays, Code postal, Commune, Lieu-dit / rue, Nom, Prénom, Nom conjoint, Prénom conjoint, Père (nom prénom), Mère (nom prénom), Père du conjoint, Mère du conjoint, Nom de fichier, Lieu (GEDCOM), ID GEDCOM, Statut, Notes.

- Le **Statut** se choisit dans une liste déroulante, colorée selon la valeur.
- Les lignes sont triées par type d'événement (naissance, baptême, mariage, divorce, décès, inhumation, sépulture), puis par commune, puis par date. Les en-têtes ont des filtres.
- La date est du texte, pour conserver les dates partielles (`1890`, `03/1890`, `vers 1895`). Pour trier chronologiquement, utilisez la colonne **Année**.
- Pour un mariage ou un divorce, Nom et Prénom sont ceux de l'époux, et Nom conjoint et Prénom conjoint ceux de l'épouse.

## Mettre à jour un classeur existant

Principe : le classeur enregistré la dernière fois sert de mémoire (statuts et notes), le GEDCOM sert de référence pour la liste des événements.

**Marche à suivre (page web)**

1. Première fois : déposez le GEDCOM sur la page principale, faites vos modifications (statuts, notes), puis exportez le classeur Excel.
2. Mises à jour : déposez le nouveau GEDCOM sur la page principale, et le classeur enregistré via le bouton *Mettre à jour un classeur* (ou directement sur la feuille à carreaux). L'ordre n'a pas d'importance. Exportez ensuite le nouveau classeur.

**Comment une ligne est retrouvée**

- D'abord par son type, son **ID GEDCOM**, sa date et son lieu (le texte du lieu tel qu'il est dans le GEDCOM).
- À défaut, par son type, son nom, son prénom, sa date et son lieu. Cette seconde clé sert quand l'ID a changé (nouvel export) mais que le nom est resté identique.
- Les statuts et les notes des lignes retrouvées sont recopiés dans le nouveau classeur.

**Ce qui se passe selon les modifications de l'arbre**

| Modification | Résultat |
|---|---|
| Personne ou événement supprimé du GEDCOM | La ligne n'est plus retrouvée. Avec un statut ou une note, elle est rangée dans `Sortis` ; sinon elle disparaît |
| Personne ou événement ajouté | Nouvelle ligne au statut « À rechercher » |
| Événement devenu sourcé | Comme une suppression : `Sortis` si la ligne avait un statut ou une note, sinon elle disparaît |
| Nom ou prénom modifié, même ID, même date et même lieu | Ligne retrouvée par l'ID : statut et note conservés, nouveau nom affiché |
| Date ou lieu modifié (commune, code postal, tout le texte du lieu) | Aucune clé ne correspond : l'ancienne ligne va dans `Sortis` (si statut ou note) et une nouvelle ligne « À rechercher » apparaît. Recopiez la note à la main depuis `Sortis` |
| ID modifié, nom, date et lieu identiques | Ligne retrouvée par le nom |
| ID et nom modifiés | Ligne non retrouvée : comme une suppression suivie d'un ajout |

La feuille **Sortis** garde l'ancien onglet de chaque ligne. Rien n'est perdu tant qu'elle est conservée ; supprimez les lignes devenues inutiles. Les lignes restées à « À rechercher » sans note qui disparaissent ne sont pas conservées.

## Le nom de fichier proposé

Chaque événement reçoit un nom de fichier calculé à partir d'un **modèle** propre à son type. Sans changement de réglage, on obtient :

| Type | Modèle par défaut | Exemple |
|---|---|---|
| Naissance | `{aaaa}_{mm}_{jj} {ville} {lettre} {nom} {prenom}` | `1890_03_12 Soultz N DUPONT Jean_Pierre` |
| Baptême | idem, lettre `B` | `1890_03_14 Soultz B DUPONT Jean_Pierre` |
| Mariage | `{aaaa}_{mm}_{jj} {ville} {lettre} {nom} {prenom} et {nom_conjoint} {prenom_conjoint}` | `1920_06_05 Soultz M DUPONT Jean et MULLER Marie` |
| Décès | idem naissance, lettre `D` | `1950_06_05 Soultz D DUPONT Jean` |
| Divorce, Inhumation, Sépulture | aucun modèle | à définir par vos soins |

Dans un modèle, chaque `{champ}` est remplacé par sa valeur ; le reste du texte (espaces, `_`, tirets, « et »…) est recopié tel quel.

### Champs disponibles

| Champ | Valeur |
|---|---|
| `{aaaa}` | Année sur 4 chiffres (1890) |
| `{aa}` | Année sur 2 chiffres (90) |
| `{mm}` | Mois sur 2 chiffres |
| `{jj}` | Jour sur 2 chiffres |
| `{pays}` | Pays en toutes lettres (Suisse) |
| `{pp}` | Code pays sur 2 lettres (CH pour la Suisse). Connu pour une soixantaine de pays courants, vide pour les autres |
| `{cp}` | Code postal |
| `{ville}` | Commune (les espaces sont remplacés selon l'option prévue) |
| `{lettre}` | Lettre choisie pour ce type d'événement |
| `{nom}`, `{prenom}` | Nom et prénoms de la personne (l'époux pour un mariage ou un divorce) |
| `{nom_conjoint}`, `{prenom_conjoint}` | Nom et prénoms du conjoint (l'épouse pour un mariage ou un divorce) |
| `{lieudit}` | Lieu-dit ou rue |
| `{dept}` | Numéro du département |
| `{type}` | Naissance, Baptême, Mariage… |
| `{id}` | Identifiant GEDCOM de la personne ou de la famille |

### Options

| Option | Effet |
|---|---|
| Séparateur entre les prénoms | `_` donne `Jean_Pierre`, `-` donne `Jean-Pierre` |
| Espaces d'une commune remplacés par | `_` donne `La_Chapelle`. Un espace seul les garde, un texte vide les supprime |
| Noms de famille en majuscules | Coché : `DUPONT` ; décoché : tel que dans le GEDCOM |
| Exiger une date complète | Coché : il faut le jour, le mois et l'année. Décoché : un jour ou un mois inconnu devient `00` |
| Pays et code pays seulement si différent de la France | Coché : `{pays}` et `{pp}` ne s'écrivent pas pour la France, même s'ils sont dans le modèle. Le séparateur qui les suit est omis aussi, donc un même modèle sert pour la France et pour l'étranger |

### Quand aucun nom n'est proposé

- Le modèle du type est vide.
- Un champ utilisé dans le modèle est vide (une commune manquante, un `{pp}` pour un pays non reconnu, un prénom absent…).
- La date est approximative (`vers`, `avant`, `après`, `entre`…) : jamais de nom dans ce cas.
- Un champ du modèle est inconnu.

Les caractères interdits dans un nom de fichier Windows (`\ / : * ? " < > |`) sont retirés automatiquement.

La page indique la raison dans la fiche de l'événement (« Non proposé : date absente ou approximative »).

### Où régler

Dans la page, cliquez sur le bouton *Nom de fichier*, à droite du titre : une fenêtre s'ouvre. Un clic sur un champ l'insère dans le modèle, et un aperçu se met à jour à chaque frappe.

Les réglages sont **gardés automatiquement** par le navigateur : vous les retrouvez à la prochaine ouverture de la page, avec le même navigateur sur le même ordinateur. Ils sont perdus si vous effacez les données du navigateur, et ne suivent pas d'un navigateur ou d'un ordinateur à l'autre.

### Sauvegarder les réglages dans un fichier

Pour ne pas perdre vos réglages, ou les retrouver sur un autre navigateur ou un autre ordinateur :

1. Cliquez sur le bouton *Nom de fichier*, puis sur **Enregistrer les réglages dans un fichier**.
2. Le fichier `Actes_a_rechercher_reglages_nom_fichier.json` arrive dans votre dossier « Téléchargements ». Rangez-le à côté de `Actes_a_rechercher.html`, avec vos autres fichiers.

Pour les retrouver, deux possibilités :

- **Glisser le fichier de réglages sur la feuille à carreaux**, en même temps que votre GEDCOM (sélectionnez les deux fichiers, puis faites-les glisser ensemble) ou avant lui. Les réglages sont appliqués puis le GEDCOM est lu avec ces réglages.
- Ou cliquer sur *Nom de fichier*, puis sur **Charger des réglages depuis un fichier**.

La page ne peut pas aller chercher seule un fichier sur votre ordinateur : c'est une protection du navigateur. Le chargement n'est donc « automatique » que lorsque vous glissez le fichier de réglages avec votre GEDCOM.

## Règles d'extraction

**Événements lus dans le GEDCOM**

| Type | Balise GEDCOM |
|---|---|
| Naissance | `BIRT` |
| Baptême | `CHR`, `BAPM` |
| Mariage | `MARR` (dans la famille) |
| Divorce | `DIV` (dans la famille) |
| Décès | `DEAT` |
| Inhumation | `BURI` |
| Sépulture | `EVEN` avec `TYPE` « Sépulture » |

La norme GEDCOM n'a pas de balise pour la sépulture : elle n'est reconnue que si votre fichier la note comme événement personnalisé. La page liste les types d'événement présents dans le fichier mais non extraits (par exemple `CREM`, ou `EVEN « Recensement »`), pour repérer une balise que l'outil ne connaîtrait pas.

**Événement sans source.** Un événement est retenu s'il a une date ou un lieu, et aucune balise `SOUR` sous l'événement lui-même. Une source posée sur la personne ou sur la famille ne compte pas comme source de l'événement. Un événement sans date ni lieu est ignoré.

**Une ligne par événement.** Naissance, baptême, décès, inhumation et sépulture : une ligne par personne. Mariage et divorce : une ligne par famille.

**Dates.** Sont reconnus `12 MAR 1890`, `MAR 1890`, `1890`, avec les préfixes `ABT`, `CAL`, `EST`, `BEF`, `AFT`, et les plages `BET … AND …` et `FROM … TO …`. Une date non reconnue (le calendrier républicain, par exemple) est conservée telle quelle. Dans la page, les événements sans date sont placés en fin de liste.

**Lieux.** Le format attendu est :

```
Commune, Code postal, Département, Région, Pays, Lieu-dit ou rue
```

Quand le lieu a au moins cinq éléments avec le pays en cinquième position, il est lu par position, ce qui tolère les éléments vides. Sinon, l'outil cherche le pays, le département et le code postal par leur nom ou leur forme. Le département est reconnu par son nom (noms actuels et quelques anciens noms) ou déduit du code postal. **Hypothèse :** si le pays est absent mais qu'un département, une région ou un code postal est reconnu, le lieu est considéré comme français. Un pays explicite l'emporte toujours : un événement alsacien d'avant 1918 saisi avec « Allemagne » ira dans la feuille `Allemagne`.

Si les lieux de votre fichier suivent un autre format, le classement des feuilles peut être faux : la colonne *Lieu (GEDCOM)* du classeur garde le lieu d'origine pour vérifier.

## Confidentialité

- La page web lit le fichier dans votre navigateur. Elle n'effectue aucune requête réseau : la bibliothèque Excel et les polices sont dans le fichier HTML. C'est vérifié dans Chromium, pas dans les autres navigateurs.
- Le classeur reste sur votre ordinateur tant que vous ne l'envoyez pas vous-même quelque part. Si vous l'importez dans Google Sheets, il est envoyé à Google.
- Un GEDCOM et le classeur qui en découle contiennent des données personnelles, parfois sur des personnes vivantes. **Ne les publiez pas** dans un dépôt public ni ailleurs. Le fichier `.gitignore` fourni exclut les fichiers `.ged`, `.gedcom` et `Actes_a_rechercher_*.xlsx`.

## Compatibilité et limites

- Page web : testée avec Chromium. Firefox, Safari et Edge ne sont pas testés.
- Le classeur s'ouvre dans Excel et dans LibreOffice Calc. Les compteurs de la page `Suivi` sont des formules, calculées à l'ouverture.
- Vous n'avez pas Excel ? Le classeur peut aussi être **importé dans Google Sheets** (gratuit, avec un compte Google) : les liens entre les onglets y fonctionnent (testé). Attention : dans ce cas, le classeur est envoyé chez Google, donc vos données quittent votre ordinateur (voir [Confidentialité](#confidentialité)).
- Seuls Excel et Google Sheets ont été essayés avec les liens entre les onglets. LibreOffice Calc n'a pas été essayé pour ces liens.
- Les codes pays `{pp}` couvrent environ 60 pays courants ; pour les autres, `{pp}` est vide et aucun nom n'est proposé s'il figure dans le modèle.
- Les noms de fichier n'existent que pour les dates exactes tant que l'option *Exiger une date complète* est cochée.
- L'encodage ANSEL, rare, n'est lu qu'approximativement : les accents peuvent être mal restitués.
- Il n'y a pas de sauvegarde automatique dans la page : exportez le classeur pour conserver vos modifications.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `Actes_a_rechercher.html` | La page web, autonome |
| `README.md` | Ce mode d'emploi |

À la racine du dépôt, commun à tous les outils : `LICENSE` (licence MIT) et `.gitignore` (exclut les données personnelles : fichiers `.ged`, `.gedcom`, classeurs et exports CSV, si vous utilisez git).

## Composants tiers

- [ExcelJS](https://github.com/exceljs/exceljs) 4.4.0, licence MIT, embarqué dans la page web pour écrire et lire les fichiers Excel, avec deux petites modifications (les liens internes du classeur sont écrits sans référence externe et avec leur texte affiché, comme le fait Excel).
- Polices [Libre Caslon Text](https://fonts.google.com/specimen/Libre+Caslon+Text) et [Atkinson Hyperlegible](https://fonts.google.com/specimen/Atkinson+Hyperlegible), licence SIL Open Font License, embarquées dans la page web.

Si vous redistribuez le projet, joignez les avis de licence de ces composants.

## Licence

Ce projet est distribué sous licence **MIT** (voir le fichier `LICENSE` à la racine du dépôt) : vous pouvez l'utiliser, le copier, le modifier et le partager librement, à condition de conserver le nom de l'auteur et la mention de licence. Il est fourni tel quel, sans garantie.

## Auteur

[St3ffyCode](https://github.com/St3ffyCode)
