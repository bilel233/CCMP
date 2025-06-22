## Exercice 9 : Conditions simples

**Énoncé :**

Écrivez un programme en langage Tiger qui :

1. Déclare une variable entière `age`.  
2. Initialise cette variable avec une valeur au choix.  
3. Affiche **"Majeur"** si l’âge est supérieur ou égal à 18, sinon affiche **"Mineur"**.

**Solution proposée :**

```tiger
let
  var age := 20
in
  if age >= 18 then
    print("Majeur\n")
  else
    print("Mineur\n")
end
