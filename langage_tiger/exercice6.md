## Exercice 3 : Fonctions simples

**Énoncé :**

Écrivez une fonction en langage Tiger nommée `double` qui :

1. Prend un entier `x` en paramètre.  
2. Retourne la valeur de `x` multipliée par 2.  

Puis, dans le même programme, appelez `double(5)` et affichez le résultat.

**Solution proposée :**

```tiger
let
  function double(x: int): int = x * 2
in
  print_int(double(5))
end
