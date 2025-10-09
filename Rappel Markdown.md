# Rappel Markdown version GitHub
## Syntaxe de base
### Début de ligne
`# Titre niveau 1` # Titre niveau 1\
`## Titre niveau 2` ## Titre niveau 2\
`### Titre niveau 3`  ### Titre niveau 3\
`> Citation` > Citation\
`- texte`\

### Autour du texte à mettre en évidence
`**texte** ou __texte__`  **gras**\
`*texte* ou _texte_`  *italique*\
`~~texte~~`  ~~barré~~\
`**du texte gras avec _du texte en italique_ imbriqué**`  **du texte gras avec _du texte en italique_ imbriqué**\
`***tout un texte***`  ***texte en gras et italique***\
`texte<sub>indice</sub>`  texte<sub>indice</sub>\
`texte<sup>exposant</sup>`  texte<sup>exposant</sup>\
On peut citer du code ou une commande dans une phrase avec des accents graves uniques ` `. Le texte entre les accents graves ne sera pas mis en forme.  
\`du code\`  `du code`

Pour un bloc de code:  
\```  
un peu  
de code  
\```  


```
un peu
de code
```
### Saut de ligne
On peut ajouter un saut de ligne entre deux lignes de différentes manières, avec 2 espaces sur la première, un \ ou un <br/> 

### Listes
On peut créer une liste non triée en faisant précéder une ou plusieurs lignes de texte de -, * ou +.  
\- élément 1\
\+ élément 2\
\* élément 3\

- élément 1
+ élément 2
* élément 3

Pour des listes numérotées on commence avec un chiffre suivi d'un point.  
1\. élement 1\
2\. élement 2

1. élement 1
2. élement 2

## Tableaux

```
| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
```


| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

La largeur des cellules peut varier et ces dernières n’ont pas besoin d’être parfaitement alignées dans les colonnes.\
Il doit y avoir au moins trois traits d’union dans chaque colonne de la ligne d’en-tête.

```
| Command | Description |
| --- | --- |
| `git status` | List all *new or modified* files |
| `git diff` | Show file differences that **haven't been** staged |
```

| Command | Description |
| --- | --- |
| `git status` | List all *new or modified* files |
| `git diff` | Show file differences that **haven't been** staged |

On peut aligner le texte à gauche, à droite ou au centre d’une colonne en incluant des deux-points : à gauche, à droite\
ou des deux côtés des traits d’union dans la ligne d’en-tête.

```
| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |
```

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |

### caractère d'échapement \
Si on veut qu'un caractère ne soit pas pris en compte et puisse s'afficher normalement, on utilise \
Par ex pour inclure une barre verticale | en tant que contenu dans une cellule

```
| Name     | Character |
| ---      | ---       |
| Backtick | `         |
| Pipe     | \|        |
```

| Name     | Character |
| ---      | ---       |
| Backtick | `         |
| Pipe     | \|        |

Ou autre exemple pour afficher le \` sans que ca passe pour du code.
