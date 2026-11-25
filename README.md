# ConsData

Paquet de **données dérivées** pour la construction (valeurs, paramètres,
formules, résumés et références), compilé par
[ConsData.collector](https://github.com/samagior/ConsData.collector) et utilisé
par les outils Dynalisp.

> Ce dépôt est **public**. Il ne contient pas les documents d'origine ni leur
> texte intégral : seulement des données dérivées rédigées, avec un renvoi précis
> à la source (document, section, page). Le texte et les figures d'un document n'y
> figurent que si sa licence le permet (domaine public, licence ouverte ou
> autorisation écrite).

## Contenu

```
consdata-pack/
├── manifest.json            liste des documents + empreinte SHA-256 de chaque fichier
├── NOTICE.md                sources, éditeurs et titulaires de droits
└── documents/<id>/
    ├── reference.json       référence bibliographique, licence, classification
    ├── outline.json         plan du document (titres et pages)
    ├── tables.json          tableaux de valeurs autorisés (+ tables/*.csv)
    ├── derived/             paramètres, formules et résumés rédigés
    └── content.json, figures/   seulement pour les documents en licence ouverte
```

Chaque document est classé par **catégorie** (gouvernement, normalisation,
manufacturier…), **auteur**, **type** (code, norme, fiche technique…) et
**sujets** ; voir `classification` dans `manifest.json` et `reference.json`.

## Utilisation dans Dynalisp

1. Lire `consdata-pack/manifest.json` et filtrer par classification.
2. Vérifier l'intégrité des fichiers avec les empreintes SHA-256.
3. Charger `derived/parameters.json` ; chaque valeur porte sa `source`.

## Mise à jour

Le paquet est régénéré depuis le dépôt privé de travail :

```bash
consdata dist --publish   # copie le paquet dans ce dépôt
git -C ~/ConsData diff    # relire avant de publier
```

## Licence

Les données dérivées rédigées pour ce paquet (paramètres, formules, résumés,
structure et métadonnées) sont publiées sous licence
[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE) :
réutilisation libre, y compris commerciale, à condition de citer
« ConsData (samagior) ».

Cette licence ne couvre pas les documents d'origine. Leurs titulaires de droits
sont indiqués dans `NOTICE.md` et dans chaque `reference.json` ; un contenu
reproduit avec l'accord d'un éditeur ou sous licence ouverte reste soumis à sa
propre licence, précisée dans `reference.json` (`licence`).

## Avertissement

Ces données facilitent le travail mais ne remplacent pas les documents
officiels. Pour tout usage normatif, consulter la version en vigueur du
document d'origine auprès de son éditeur (voir `NOTICE.md`).
