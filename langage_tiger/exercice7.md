## Exercice 7 : Types définis par l’utilisateur (record)

**Énoncé :**

1. Déclarez un type `personne` ayant deux champs :  
   - `age` de type `int`  
   - `nom` de type `string`  
2. Créez une variable `p` de ce type et initialisez-la avec vos propres valeurs.  
3. Affichez l’âge (`p.age`) de cette personne.

**Solution proposée :**

```tiger
let
  type personne = { age: int, nom: string }
  var p := personne { age = 26, nom = "Bilel" }
in
  print_int(p.age)
end
