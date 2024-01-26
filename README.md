# Règles de programmation
## Entête de fichier java
Appliquer l'entête suivant aux fichiers sources:
```
/*
 * Classname: 420-A14-BB ASSURANCE QUALITÉ ET TECHNIQUES DE TESTS
 *
 * Projet: Rapport de revue
 * 
 * Version information:
 *
 * Date:
 * 
 * Author:
 */
```
  
## Identation
- Éviter les lignes de plus de 80 charactères lorsque possible
- Briser la ligne seulement après une virgule ou après un opérateur
- Aligner le début de la ligne suivante au même niveau que la ligne précédante

Exemples d'indentation:
```
someMethod(longExpression1, longExpression2, longExpression3,

        longExpression4, longExpression5);
 
var = someMethod1(longExpression1,
                someMethod2(longExpression2,
                        longExpression3));
```
> [!IMPORTANT]
> Lorsqu'une parenthèse est ouverte, ce point devient le nouveau 'début' si jamais nous devons briser la ligne à nouveau.

## Commentaires
Un programme peut avoir 4 implementation de commentaires: block, single-line, trailing, et end-of-line.

### Commentaires Block
Les commentaires de bloc sont utilisés pour fournir des descriptions de fichiers, de méthodes, de structures de données et d'algorithmes. Les commentaires de bloc peuvent être utilisés au début de chaque fichier et avant chaque méthode. Ils peuvent également être utilisés à d'autres endroits, tels que à l'intérieur des méthodes. Les commentaires de bloc à l'intérieur d'une fonction ou d'une méthode doivent être indentés au même niveau que le code qu'ils décrivent.

Un commentaire de bloc doit être précédé d'une ligne vide pour le distinguer du reste du code.
```
/*

 * Ceci est un commentaire en bloque.
 */
```

### Commentaires Single-line
Les commentaires courts peuvent apparaître sur une seule ligne, indentée au niveau du code qui suit. Si un commentaire ne peut pas être écrit sur une seule ligne, il doit suivre le format du commentaire de bloc.

```
if (condition) {/* Gère la condition. */
...
}
```

### Commentaires Trailing
Des commentaires très courts peuvant apparaître sur la même ligne que le code qu'ils décrivent, mais ils doivent être suffisamment décalés pour les séparer des instructions. Si plusieurs commentaires courts apparaissent dans un morceau de code, ils doivent tous être indentés selon le même réglage de tabulation.

Voici un exemple de commentaire en fin de ligne dans du code Java :
```
if (a == 2) {return TRUE;            /* special case */
} else {
return isPrime(a);      /* works only for odd a */
}
```

## Déclarations
### Bris de ligne
Une déclaration par ligne est préféré vu que ça encourage les commentaires.  En d'autres mots,
```
int level; // indentation level
int size;  // size of table
```
est préféré à
```
int level, size;
```
### Initialisation
Essayer d'initialiser une valeur à chaque variable dès leur déclaration.  La seule raison de ne pas en attribuer une est si sa valeur initiale dépend d'un calcul.

### Placement
Placer les déclarations directement au début des blocs.  N'attendez pas leur première utilisation.
```
void maMethod() {
    int int1 = 0;         // début du bloque méthode

    if (condition) {
        int int2 = 0;     // début du bloque "if"
        ...
    }
}
```
> [!NOTE]
> La seule exception est pour l'index des for loops, qui peut être déclaré directement dans le statement.

### Classes et interfaces
Lors de la déclaration de classes ou d'interfaces Java, le guide de formattage suivant devrait être suivi:
- Pas d'espace entre le nom de la méthode et la parenthèse "(" qui ouvre les paramètres
- La braquette ouverte "{" devrait apparaitre à la fin de la même ligne que la ligne déclarative
- La braquette fermée "}" devrait apparaître sur une ligne seule aligné au statement, à moins d'être une méthode null
- Les méthodes sont séparées d'une ligne vide

Exemple de déclarations optimale:
```
class Exemple extends Object {
    int ivar1;
    int ivar2;

    Exemple(int i, int j) {
        ivar1 = i;
        ivar2 = j;
    }

    int emptyMethod() {}

    ...
}
```
