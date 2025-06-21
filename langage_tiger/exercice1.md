## Exercice 1 – Analyse lexicale

### Énoncé

1. Écris les expressions régulières (en syntaxe POSIX ou équivalente) pour reconnaître :

   * un **identificateur** (lettre suivie de lettres, chiffres ou « \_ »)
   * un **entier décimal** (suite de chiffres)
   * une **chaîne de caractères** délimitée par `"`, permettant les séquences `\n` et `\"`.

2. Pour la ligne suivante :

   ```tiger
   print("Hello,\nWorld!" + name)
   ```

   découpe-la en tokens (nom du token + lexème).

---

## Solution

### 1. Expressions régulières

* **Identificateur**

  ```regex
  [A-Za-z][A-Za-z0-9_]*
  ```

  * Commence par une lettre (`A`–`Z` ou `a`–`z`)
  * Suivi de 0 ou plusieurs lettres, chiffres ou underscore

* **Entier décimal**

  ```regex
  [0-9]+
  ```

  * Une suite d’un ou plusieurs chiffres

* **Chaîne de caractères**

  ```regex
  "([^"\\]|\\n|\\")*"
  ```

  * Délimitée par des guillemets `"`
  * Contient soit :

    * `[^"\\]` : tout caractère sauf `"` ou `\\`
    * `\\n` : séquence d’échappement pour saut de ligne
    * `\\"` : séquence d’échappement pour guillemet

### 2. Tokenisation de la ligne

Ligne Tiger :

```tiger
print("Hello,\nWorld!" + name)
```

| Ordre | Token        | Lexème             |
| :---: | :----------- | :----------------- |
|   1   | `IDENT`      | `print`            |
|   2   | `LPAREN`     | `(`                |
|   3   | `STRING_LIT` | `"Hello,\nWorld!"` |
|   4   | `PLUS`       | `+`                |
|   5   | `IDENT`      | `name`             |
|   6   | `RPAREN`     | `)`                |

**Détail du découpage** :

1. `print` → `[A-Za-z][A-Za-z0-9_]*` → **IDENT**
2. `(` → **LPAREN**
3. `"Hello,\nWorld!"` → `"(…)"` avec `\\n` → **STRING\_LIT**
4. `+` → **PLUS**
5. `name` → **IDENT**
6. `)` → **RPAREN**
