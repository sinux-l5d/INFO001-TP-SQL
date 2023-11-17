Dans une application Web, où sont généralement stockées les données persistantes des utilisateurs (nom, prénom, n° CB, notes …)?

**Généralement dans une base de données.**

---

Proposer une traduction pour le terme tampering.  **Falsification.**
Quelle commande SQL permet d’effectuer une recherche en fonction de critères ? **SELECT**
Quelle commande SQL permet d’ajouter des données dans une table ? **INSERT**

---

Dans la vidéo SQL Injection, un exemple d’attaque/de vulnérabilité est donné. 

Quel type de requête HTTP est émise lorsque l’utilisateur appuie sur le bouton login ? 

**POST**

Quelle est la requête SQL effectuée à partir des données saisies par l’utilisateur ? 

`SELECT * FROM users WHERE login = ‘toto’ AND password = ‘toto’`

En se basant sur l’exemple de table users donnée précédemment, donnez le contenu de la variable $result ?

**Result contient une structure de données représentant la ligne correspondante à la requête SQL.**

Que devrait-on tester pour valider l’authentification d’un utilisateur ? **Il faut tester si la variable $result est vide ou non.**

---

Expliquer en 80 mots ± 10% le fonctionnement d’une attaque SQL injection (vous prendrez comme exemple l’attaque SQL injection présentée dans la vidéo).

**On altère la structure de la requête en utilisant des les caractères de fin de chaîne, ce qui permet d'écrire une nouvelle requête juste après. Cela fonctionne quand le développeur n'as pas pensé à assainir ce que donne l'utilisateur.**

Donner le nombre de mots utilisés. **39**

Que contient la variable $result lorsque l’attaque a lieu ? **Dans l'exemple de la vidéo, tout les utilisateurs**

---

En quoi une attaque SQL Injection est-elle semblable à une attaque de type Buffer Overflow ? 

**Elle est semblable car fondamentallement le problème est le même : on ne vérifie pas la taille/le type de ce que l'utilisateur donne.**

---

Quelles sont les méthodes présentées pour empêcher les attaques de type SQL Injection ?

**On peut utilisé des blacklist/whitelist (ce dernier est à privilégié), des prepares statements (on donne la requête au préalable, avant de fournir les variables, garantissant ainsi que la structure de la requête soit préservé) ou échapper les chaines d'entrées (`'` deviens `\'`)**

Pour les deux premières méthodes donner les avantages et les inconvénients en citant les exemples donnés dans les vidéos ? 

**Blacklist :** On interdit les caractères spéciaux, mais on peut oublier des caractères, et on peut avoir des faux positifs (par exemple, si on interdit les `'`, on ne peut plus utiliser d'apostrophe dans les noms).

**Whitelist :** On autorise seulement les caractères que l'on veut, mais on peut oublier des caractères, et on peut avoir des faux positifs (par exemple, si on autorise les `'`, on peut avoir des injections SQL).

**Prépare statements :** On donne la requête au préalable, avant de fournir les variables, garantissant ainsi que la structure de la requête soit préservé.

**Échapper les chaines d'entrées :** On échappe les caractères spéciaux, mais on peut se retrouvé avec un nom d'utilisateur qui contient des caractères spéciaux. Innofensif, mais pas très esthétique.

Quelles sont les méthodes recommandées ?

**Prépare statements et échapper les chaines d'entrées.**



---
