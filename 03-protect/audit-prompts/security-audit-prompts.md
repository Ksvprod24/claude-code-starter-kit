# Securite — 10 prompts d'audit

Prompts pour auditer et securiser n'importe quel projet web. Adaptes pour Next.js + Supabase + Stripe mais fonctionnent avec tout stack.

---

## Prompt 01 — Audit OWASP Top 10

```
CONTEXTE : Mon projet utilise [STACK] (ex: Next.js + Supabase + Stripe).
L'app est deployee sur [HEBERGEUR]. Elle gere [TYPE_DONNEES] (ex: donnees utilisateurs, paiements).

TACHE : Audite mon projet contre les OWASP Top 10 2025 :
1. Broken Access Control
2. Cryptographic Failures
3. Injection (SQL, XSS, Command)
4. Insecure Design
5. Security Misconfiguration
6. Vulnerable Components
7. Auth Failures
8. Data Integrity Failures
9. Logging Failures
10. SSRF

Pour chaque : risque (CRITIQUE/HAUT/MOYEN/BAS) + test a faire + fix en une ligne de code.

CONTRAINTES : Pas de theorie. Chaque point = un test concret a executer.
CRITERES DE SUCCES : Je peux executer les 10 tests en moins de 2 heures.
UTILISATION : Checklist securite avant chaque mise en production.
```

---

## Prompt 02 — Scan des dependances vulnerables

```
CONTEXTE : Mon projet est dans [CHEMIN]. Il utilise [npm/pnpm/yarn].

TACHE : Analyse les dependances et donne :
1. Liste des packages avec vulnerabilites connues (CVE)
2. Severite de chaque vulnerabilite
3. Version corrigee si disponible
4. Commande exacte pour mettre a jour

Commandes a executer :
- npm audit / pnpm audit
- Verifier les dependances non maintenues (>1 an sans update)

CONTRAINTES : Pas de "c'est probablement ok". Chaque vulnerabilite = action claire.
CRITERES DE SUCCES : Zero vulnerabilite critique/haute apres les corrections.
UTILISATION : Executer avant chaque deploy.
```

---

## Prompt 03 — Audit authentification et autorisation

```
CONTEXTE : Mon app utilise [SUPABASE_AUTH / NextAuth / AUTH_CUSTOM].
Roles utilisateurs : [ROLES] (ex: admin, user, guest).

TACHE : Verifie ces points :
1. Les routes protegees sont-elles reellement protegees ? (tester sans token)
2. Un user normal peut-il acceder aux routes admin ? (escalation de privilege)
3. Les tokens JWT expirent-ils ? Combien de temps ?
4. Le refresh token est-il stocke de maniere securisee ? (httpOnly cookie vs localStorage)
5. La deconnexion invalide-t-elle reellement le token ?
6. Y a-t-il une protection brute force sur le login ?
7. Le reset password est-il securise ? (token a usage unique, expiration)

Pour chaque : test curl/fetch a executer + resultat attendu + fix si vulnerable.

CONTRAINTES : Tests executables en copier-coller. Pas de theorie.
CRITERES DE SUCCES : Chaque test a un PASS ou FAIL clair.
UTILISATION : Tester apres chaque modification du systeme d'auth.
```

---

## Prompt 04 — Audit API et endpoints

```
CONTEXTE : Mon API expose les endpoints suivants : [LISTE_ENDPOINTS].
Authentification par [JWT/API_KEY/SESSION].

TACHE : Verifie pour chaque endpoint :
1. Rate limiting en place ? (combien de requetes/minute autorisees)
2. Validation des inputs ? (types, longueurs, caracteres speciaux)
3. Protection contre l'enumeration ? (ex: /api/users/1, /api/users/2...)
4. Les erreurs exposent-elles des infos sensibles ? (stack traces, SQL errors)
5. CORS configure correctement ? (pas de wildcard *)
6. Les reponses contiennent-elles des donnees en trop ? (over-fetching)

CONTRAINTES : Un test curl par endpoint. Resultat binaire : securise ou pas.
CRITERES DE SUCCES : Tous les endpoints passent les 6 points.
UTILISATION : Audit avant chaque release d'API.
```

---

## Prompt 05 — Audit paiements Stripe

```
CONTEXTE : Mon app utilise Stripe pour [ABONNEMENTS/PAIEMENTS_UNIQUES/LES_DEUX].
Les webhooks sont configures sur [URL_WEBHOOK].

TACHE : Verifie :
1. Le prix est-il calcule cote serveur ? (jamais cote client)
2. Les webhooks verifient-ils la signature Stripe ?
3. Un utilisateur peut-il modifier le montant du paiement ?
4. Les webhooks sont-ils idempotents ? (que se passe-t-il si Stripe renvoie 2x le meme event)
5. La cle secrete Stripe est-elle dans les variables d'environnement ? (pas dans le code)
6. Le mode test et le mode live sont-ils bien separes ?
7. Les remboursements sont-ils traces ?

Pour chaque : test a executer + risque si non securise + fix.

CONTRAINTES : Chaque test doit prouver que le paiement ne peut pas etre manipule.
CRITERES DE SUCCES : Impossible de payer 0€ ou de modifier un prix.
UTILISATION : Audit avant de passer en mode live Stripe.
```

---

## Prompt 06 — Audit variables d'environnement et secrets

```
CONTEXTE : Mon projet est dans [CHEMIN]. Il utilise [.env / .env.local / Vercel env / Hostinger].

TACHE : Verifie :
1. Y a-t-il un .env dans le git ? (git log --all -- .env)
2. Le .gitignore contient-il tous les fichiers sensibles ?
3. Les variables NEXT_PUBLIC_* contiennent-elles des secrets ? (elles sont exposees au client)
4. Les cles API ont-elles les permissions minimales ?
5. Y a-t-il des secrets en dur dans le code ? (grep pour "sk_", "key=", "password=", "secret")
6. Les secrets de production sont-ils differents de ceux de dev ?

CONTRAINTES : Commandes grep exactes a copier-coller.
CRITERES DE SUCCES : Zero secret expose, zero secret dans git.
UTILISATION : A faire une fois + avant chaque nouveau deploy.
```

---

## Prompt 07 — Audit RGPD / vie privee

```
CONTEXTE : Mon app collecte [TYPES_DONNEES] (email, nom, adresse, paiement...).
Mes utilisateurs sont en [PAYS/ZONE] (EU, US, etc.).

TACHE : Verifie la conformite :
1. Consentement cookies — banner presente ? Refus possible ?
2. Politique de confidentialite — existe ? A jour ? Mentionne chaque type de donnee ?
3. Droit de suppression — l'utilisateur peut-il supprimer son compte et toutes ses donnees ?
4. Droit d'export — l'utilisateur peut-il telecharger ses donnees ?
5. Duree de retention — combien de temps les donnees sont-elles conservees ?
6. Sous-traitants — liste des services tiers qui accedent aux donnees (Stripe, Supabase, analytics)
7. DPO / contact — y a-t-il un email de contact pour les demandes vie privee ?

CONTRAINTES : Chaque point = conforme ou non conforme. Pas de "c'est recommande".
CRITERES DE SUCCES : Tous les points sont conformes avant mise en production.
UTILISATION : Audit legal avant lancement + revue annuelle.
```

---

## Prompt 08 — Hardening serveur / hebergement

```
CONTEXTE : Mon site est heberge sur [HOSTINGER/VERCEL/VPS].
Domaine : [DOMAINE]. DNS gere par [PROVIDER_DNS].

TACHE : Verifie :
1. SSL/TLS — certificat valide ? Grade A sur ssllabs.com ? HSTS active ?
2. Headers securite — X-Frame-Options, CSP, X-Content-Type-Options, Referrer-Policy
3. DNS — SPF, DKIM, DMARC configures ? (anti-usurpation email)
4. Port scan — quels ports sont ouverts ? (seulement 80/443 necessaires)
5. Version serveur — le header "Server" expose-t-il la version ?
6. Backup — les backups sont-ils automatiques ? Testes recemment ?
7. Acces SSH — cle SSH uniquement ? (pas de mot de passe)

Pour chaque : commande ou URL pour tester + resultat attendu + fix.

CONTRAINTES : Tests executables sans outil payant.
CRITERES DE SUCCES : Grade A sur SSL Labs, tous les headers en place.
UTILISATION : Audit apres chaque migration ou changement d'hebergeur.
```

---

## Prompt 09 — Plan de reponse incident

```
CONTEXTE : Je suis entrepreneur solo. Je gere [X] sites/apps en production.
[X] utilisateurs au total. Donnees sensibles : [OUI/NON].

TACHE : Cree mon plan de reponse incident :
1. Detection — Comment je sais que je suis hacke ? (alertes, monitoring)
2. Premiere heure — Les 5 actions immediates (dans l'ordre)
3. Communication — Template de message pour mes clients
4. Investigation — Comment trouver ce qui s'est passe
5. Remediation — Comment boucher la faille
6. Post-mortem — Template de rapport incident
7. Prevention — 3 actions pour que ca n'arrive plus

CONTRAINTES : Actions realisables par un solo dev en situation de stress.
CRITERES DE SUCCES : Je sais exactement quoi faire a 3h du matin si je recois une alerte.
UTILISATION : Document a imprimer + sauvegarder hors-ligne.
```

---

## Prompt 10 — Score securite global

```
CONTEXTE : Mon projet est [NOM]. Stack : [STACK]. Hebergeur : [HOST].
J'ai fait les audits suivants : [LISTE_AUDITS_FAITS].

TACHE : Calcule mon score securite global /100 :
- Authentification (/20)
- Protection des donnees (/20)
- Securite API (/20)
- Infrastructure (/20)
- Conformite legale (/20)

Pour chaque categorie : score + justification + action prioritaire si < 15/20.

CONTRAINTES : Score chiffre, pas de "globalement correct". Justification factuelle.
CRITERES DE SUCCES : Score >= 80/100 avant mise en production.
UTILISATION : Dashboard securite personnel. Re-scorer tous les trimestres.
```

---

## Variables a remplacer

- `[STACK]` — technologies utilisees (Next.js, Supabase, etc.)
- `[HEBERGEUR]` — ou l'app est deployee
- `[TYPE_DONNEES]` — quelles donnees tu collectes
- `[LISTE_ENDPOINTS]` — tes routes API
- `[DOMAINE]` — ton nom de domaine
