# Contribuer

Merci de vouloir enrichir le répertoire ! Il y a trois façons de contribuer, de la plus simple à la plus technique.

## 1. Proposer une newsletter sans toucher au code

Remplissez le [formulaire d'ajout](../../issues/new?template=ajout-newsletter.yml). Une personne qui maintient le projet créera la fiche pour vous.

## 2. Ajouter une fiche directement depuis GitHub (sans installer quoi que ce soit)

1. Ouvrez le dossier [`newsletters/`](newsletters/) et cliquez sur **Add file → Create new file**.
2. Nommez le fichier `<slug>.yml` : nom de la newsletter en minuscules, sans accents, mots séparés par des tirets (ex. `la-veille-du-dev.yml`).
3. Copiez le contenu de [`_modele.yml`](newsletters/_modele.yml) et remplissez-le.
4. Cliquez sur **Commit changes** puis **Propose changes** : GitHub crée automatiquement un fork et une pull request.

Une vérification automatique s'exécute sur votre pull request. Si elle échoue, cliquez sur **Details** pour voir ce qu'il faut corriger.

## 3. En local

```bash
git clone git@github.com:<votre-compte>/newsletters-tech-fr.git
cd newsletters-tech-fr
pip install pyyaml
cp newsletters/_modele.yml newsletters/ma-newsletter.yml
# éditez la fiche, puis :
python scripts/build.py validate
```

Ne modifiez pas la liste dans le `README.md` : elle est régénérée automatiquement après chaque fusion.

## Format d'une fiche

| Champ | Obligatoire | Description |
| --- | --- | --- |
| `nom` | oui | Nom de la newsletter |
| `url` | oui | Page d'inscription ou d'accueil, en `https://` |
| `description` | oui | Une phrase, 200 caractères max |
| `thematiques` | oui | 1 à 3 valeurs parmi [`thematiques.yml`](thematiques.yml). La première détermine la section du README |
| `frequence` | oui | `quotidienne`, `hebdomadaire`, `bimensuelle`, `mensuelle` ou `irreguliere` |
| `auteur` | non | Auteur·rice ou organisation |
| `gratuite` | non | `false` si l'accès est payant (par défaut on suppose qu'elle est gratuite) |

## Critères d'inclusion

Une newsletter est acceptée si :

- elle est **rédigée en français** ;
- elle traite **principalement de tech** (au sens large : dev, data, produit, business de la tech…) ;
- elle est **active** : au moins une édition dans les 6 derniers mois ;
- elle est **éditoriale** : pas une simple newsletter promotionnelle d'un produit.

Vous pouvez proposer votre propre newsletter, c'est même encouragé.

## Corriger ou retirer une fiche

- Info erronée ou lien mort : [signalez-le](../../issues/new?template=signaler-probleme.yml) ou modifiez directement le fichier concerné.
- Newsletter arrêtée : ouvrez une pull request qui supprime sa fiche.
- Nouvelle thématique : proposez-la dans une pull request qui modifie `thematiques.yml`.

## Licence des contributions

En proposant une contribution, vous acceptez qu'elle soit publiée sous la licence du projet : [CC BY 4.0](LICENSE) pour les données, [MIT](LICENSE-CODE) pour le code.

## Code de conduite

En participant, vous vous engagez à respecter le [code de conduite](CODE_OF_CONDUCT.md).
