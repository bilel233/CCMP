## Exercice 1

### Énoncé

Pour la ligne suivante, donne la suite des tokens (type + lexème) :

```tiger
x := 10 + y
```

---

### Correction

Ligne Tiger :

```tiger
x := 10 + y
```

| Ordre | Token     | Lexème |
| :---: | :-------- | :----- |
|   1   | `IDENT`   | `x`    |
|   2   | `ASSIGN`  | `:=`   |
|   3   | `INT_LIT` | `10`   |
|   4   | `PLUS`    | `+`    |
|   5   | `IDENT`   | `y`    |

**Détail** :

1. `x` correspond à l’expression régulière `[A-Za-z][A-Za-z0-9_]*` → **IDENT**
2. `:=` est l’opérateur d’affectation de Tiger → **ASSIGN**
3. `10` correspond à l’expression régulière `[0-9]+` → **INT\_LIT**
4. `+` opérateur d’addition → **PLUS**
5. `y` identificateur → **IDENT**
