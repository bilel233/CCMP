## Exercice 2

### Énoncé

Écris **juste** l’expression régulière POSIX pour :

1. un **identificateur** (lettre puis lettres/chiffres/\_ )
2. un **entier** (suite de chiffres)

---

### Correction

1. **Identificateur**

```regex
[A-Za-z][A-Za-z0-9_]*
```

* Commence par une lettre majuscule ou minuscule
* Suivi de zéro ou plusieurs lettres, chiffres ou underscore

2. **Entier**

```regex
[0-9]+
```

* Une suite d’un ou plusieurs chiffres (0 à 9)
