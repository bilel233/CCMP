## Exercice 3 – Transpiler vs Compiler

### Énoncé

Pour chacun des exemples suivants, précise s’il s’agit plutôt d’un **transpiler** ou d’un **compilateur**, et explique pourquoi :

1. Un outil qui convertit du TypeScript en JavaScript
2. Un compilateur Go qui produit directement du code ARM exécutable
3. Un préprocesseur C qui élimine les `#include` et macros
4. Un traducteur Java → C++

---

### Correction

| Exemple                                 | Type                | Justification                                                                                                              |
| --------------------------------------- | ------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| 1. TypeScript → JavaScript              | Transpiler          | Transforme du code source TypeScript en code source JavaScript, au même niveau d’abstraction (haut niveau → haut niveau)   |
| 2. Go → code ARM exécutable             | Compilateur         | Traduit le code Go (haut niveau) directement en code machine ARM (basse niveau)                                            |
| 3. Préprocesseur C (`#include`, macros) | Outil préprocesseur | Modifie le code source C avant compilation, sans produire un nouveau code source final à un niveau d’abstraction différent |
| 4. Java → C++                           | Transpiler          | Convertit du code source Java en code source C++, même niveau d’abstraction (haut niveau → haut niveau)                    |

**Notes :**

* Un **transpiler** opère entre langages de même niveau d’abstraction.
* Un **compilateur** abaisse le niveau d’abstraction (vers assembleur ou binaire).
* Un **préprocesseur** prépare le code (supprime macros, gère includes), mais n’est ni transpiler ni compilateur final.
