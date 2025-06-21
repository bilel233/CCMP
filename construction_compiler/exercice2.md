## Exercice 2 – Chaîne de compilation GCC

### Énoncé

Indique, dans l’ordre, les quatre étapes principales du pipeline GCC pour obtenir un exécutable `a.out` à partir de `foo.c`. Pour chacune, donne le nom de l’outil utilisé.

---

### Correction

1. **Prétraitement**

   * Outil : `cpp`
   * Description : traite les directives de préprocesseur (`#include`, `#define`, etc.) et génère un fichier intermédiaire `foo.i`.

2. **Compilation**

   * Outil : `cc1`
   * Description : compile le code C preprocessé (`foo.i`) en assembleur, produisant `foo.s`.

3. **Assemblage**

   * Outil : `as`
   * Description : assemble le code assembleur (`foo.s`) en code objet binaire, produisant `foo.o`.

4. **Édition de liens**

   * Outil : `ld`
   * Description : lie un ou plusieurs fichiers objets (`foo.o` et bibliothèques) pour produire l’exécutable `a.out`.
