# breakdown

App HTML qui décompose un montant selon une **clé de répartition** avec ordre de priorité. Pensée pour les chefs d'entreprise, comptables et particuliers qui veulent répartir revenus, budgets ou frais avec rigueur.

**Live :** https://avandeneede.github.io/breakdown/

## Fonctionnalités

- **3 types de clés par ligne**
  - Montant fixe (€, $, £, ¥, etc.)
  - Pourcentage du total
  - Pourcentage de ce qui reste après les clés de priorité supérieure
- **Ordre de priorité** — les clés du haut sont servies en premier si le montant ne suffit pas
- **Multi-profils** — un profil par cas d'usage (paie, chiffre d'affaires, budget projet, charges à répartir)
- **~45 devises** internationales (EUR, USD, GBP, CHF, JPY, CNY, CAD, AUD, INR, BRL, MXN, ZAR, AED, etc.)
- **100+ icônes business** (finance, équipe, documents, tech, immobilier, transport, énergie, industrie, services…)
- **12 couleurs** système iOS pour personnaliser chaque clé
- **Multilingue** EN / FR / NL avec détection automatique (français par défaut si langue non supportée) — les clés par défaut se retraduisent automatiquement quand vous changez de langue, tant que vous ne les avez pas renommées
- **Thème clair / sombre** automatique (suit le système)
- **Saisie du montant** avec séparateur de milliers suivant la locale, flèches ↑/↓ par pas de 50
- **100 % local** — stockage `localStorage`, aucun serveur, aucune donnée envoyée
- **Mobile-first** — s'ajoute à l'écran d'accueil iOS/Android comme une app native

---

## Guide rapide

### 1. Définir le montant

Tapez le montant à répartir en haut de l'écran. L'affichage utilise les séparateurs de milliers de votre langue (`5 000` en français, `5,000` en anglais, `5.000` en néerlandais). Les flèches ↑/↓ du clavier incrémentent par pas de **50**.

Touchez le symbole de devise pour ouvrir le sélecteur (45+ devises).

### 2. Ajouter des clés

1. Touchez `+` dans la section « Clés de répartition »
2. Choisissez une **icône** parmi 100+ (maison, voiture, briefcase, mégaphone, équipe, nuage, panneau solaire, graphique, etc.) et une **couleur**
3. Donnez un nom (ex. « Loyer », « Salaires », « Marketing », « Réserve »)
4. Entrez la valeur puis choisissez :
   - `€` (ou devise du profil) pour un **montant fixe**
   - `%` `Du total` pour un **pourcentage du montant total**
   - `%` `Du reste` pour un **pourcentage de ce qui reste** après les clés de priorité supérieure

### 3. Ordre de priorité

Les clés sont traitées **de haut en bas**. Si le montant ne suffit pas à couvrir toutes les clés, celles du haut sont servies en premier ; les suivantes reçoivent ce qui reste.

Pour réorganiser, **glissez la poignée ⋮⋮** à droite de chaque ligne (sur ordinateur comme sur mobile), ou ouvrez une clé et utilisez `↑ Monter` / `↓ Descendre`.

**Exemple.** Montant 5 000 €.
- Priorité 1 — Loyer 1 800 € (fixe)
- Priorité 2 — Salaires 40 % du total
- Priorité 3 — Réserve 20 % du reste

→ Loyer reçoit 1 800 €, Salaires 2 000 €, Réserve 240 € (20 % de 1 200), libre 960 €.

### 4. Plusieurs profils

En haut à droite, tapez sur le nom du profil. Créez un profil par cas d'usage. Chaque profil a ses **propres clés, montant et devise** — utile pour séparer « paie personnelle », « chiffre d'affaires », « budget projet X », « charges à partager entre associés », etc.

Supprimez un profil via l'**icône corbeille rouge** dans la liste des profils (au moins un profil doit rester).

### 5. Langue et devise

- **Langue** : détectée automatiquement depuis le système. Si la langue de l'appareil n'est pas supportée (EN / FR / NL), l'app utilise le **français par défaut**. Pour changer manuellement : **Données → Langue**.
- **Devise** : par profil. Touchez le symbole à gauche du montant ou passez par **Données → Devise**.
- Les **clés par défaut** (Loyer, Salaires, Fournitures, Marketing, Réserve) se retraduisent automatiquement quand vous changez de langue. Dès que vous renommez une clé, le nom personnalisé est préservé.

### 6. Réinitialisation et démo

Deux actions en bas de la section **Données** pour repartir d'une base propre :

- **Charger les données de démo** (étincelle) : remplace toutes les données actuelles par un exemple de répartition complet pour une entreprise — 5 000 € à répartir entre **Loyer** (1 800 € fixe), **Salaires** (40 % du total), **Fournitures** (300 € fixe), **Marketing** (200 € fixe) et **Réserve** (30 % du reste). Utile pour redécouvrir les fonctionnalités après avoir tout supprimé, ou montrer l'app à quelqu'un sans partir de zéro.

- **Réinitialiser l'app** (rouge, icône rafraîchir) : supprime **tous les profils, toutes les clés et le montant**. L'app redémarre avec un seul profil vide nommé « Défaut ». La langue et la devise du profil sont conservées (celle de votre choix, pas remises à zéro).

> Les deux actions demandent une confirmation avant d'effacer quoi que ce soit. Si vous voulez conserver vos données actuelles, utilisez d'abord **Exporter mes profils** juste au-dessus.

---

## Exporter / Importer

Les données vivent uniquement dans le navigateur de l'appareil. L'export et l'import fonctionnent **par sélection** — vous choisissez quels profils inclure, et comment l'import se combine avec l'existant.

### Exporter un ou plusieurs profils

1. Section **Données** → **Exporter mes profils**
2. Une feuille s'ouvre avec la liste de vos profils, tous cochés par défaut
3. Décochez ceux que vous ne voulez pas exporter (ou gardez tout)
4. Touchez **Exporter** — un fichier `breakdown-YYYY-MM-DD.json` est téléchargé avec uniquement les profils cochés

C'est utile pour sauvegarder un seul profil, ou partager un profil avec un collègue sans exposer vos autres profils personnels.

### Importer sur un autre appareil

1. Section **Données** → **Importer un fichier**
2. Choisissez le fichier JSON
3. Une feuille affiche les profils contenus dans le fichier, tous cochés par défaut
4. Décochez ceux que vous ne voulez pas importer
5. Choisissez un **mode** :
   - **Tout remplacer** : supprime vos données actuelles et les remplace par les profils cochés
   - **Ajouter** : conserve vos profils existants et ajoute les nouveaux à côté (avec de nouveaux identifiants, donc aucun conflit possible — même si les noms sont identiques, les deux profils coexistent)
6. Touchez **Importer**

> En mode **Ajouter**, vous pouvez importer plusieurs fichiers successivement pour fusionner des profils provenant de différentes sources (un collègue, un ancien appareil, une sauvegarde partielle).

---

## Installer sur iPhone

1. Ouvrez l'URL dans Safari
2. Bouton Partager → **« Sur l'écran d'accueil »**
3. L'app s'ouvre ensuite en plein écran, comme une app native

## Installer sur Android

1. Ouvrez l'URL dans Chrome (ou Edge, Samsung Internet, Firefox)
2. Menu `⋮` → **« Installer l'application »** ou **« Ajouter à l'écran d'accueil »**
3. Confirmez le nom de l'app
4. L'app s'ouvre ensuite en plein écran, comme une app native

## Utilisation locale

Ouvrez simplement `index.html` dans un navigateur — aucune installation requise.

## Activer GitHub Pages

Settings → Pages → Source : branch `main`, dossier `/` (root) → Save.

---

## Historique

L'app s'appelait auparavant **repartition** (URL `avandeneede.github.io/repartition/`). GitHub redirige automatiquement l'ancienne URL vers la nouvelle. Les données `localStorage` existantes sont migrées automatiquement (clé `repartition.v6` → `breakdown.v6`).
