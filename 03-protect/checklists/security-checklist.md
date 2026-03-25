# Checklist Securite — Avant chaque mise en production

A verifier systematiquement avant chaque deploy. Cocher chaque point.

---

## Authentification
- [ ] Mots de passe hashes (bcrypt/argon2, jamais MD5/SHA1)
- [ ] Tokens JWT avec expiration courte (15min access, 7j refresh)
- [ ] Refresh tokens en httpOnly cookie (pas localStorage)
- [ ] Protection brute force (rate limit sur /login)
- [ ] Reset password avec token a usage unique + expiration
- [ ] Deconnexion invalide le token

## Autorisation
- [ ] Routes admin inaccessibles sans role admin
- [ ] API verifie les permissions cote serveur (pas cote client)
- [ ] Un utilisateur ne peut pas acceder aux donnees d'un autre
- [ ] Les ID dans les URLs ne permettent pas l'enumeration

## API
- [ ] Rate limiting sur tous les endpoints
- [ ] Validation des inputs (type, longueur, format)
- [ ] CORS restreint (pas de wildcard *)
- [ ] Erreurs sans info sensible (pas de stack trace en prod)
- [ ] Headers securite (X-Frame-Options, CSP, HSTS)

## Supabase RLS
- [ ] RLS active sur toutes les tables
- [ ] Chaque table a des policies SELECT/INSERT/UPDATE/DELETE
- [ ] Impossible de lire les donnees d'un autre utilisateur
- [ ] Le role anon n'accede pas aux donnees sensibles
- [ ] service_role utilise uniquement cote serveur

## Donnees et secrets
- [ ] Zero secret dans le code source (grep verifie)
- [ ] Zero secret dans l'historique git (TruffleHog/GitLeaks verifie)
- [ ] .env dans .gitignore
- [ ] Variables NEXT_PUBLIC_* ne contiennent pas de secrets
- [ ] Donnees sensibles chiffrees en base
- [ ] Backup automatique active et teste
- [ ] security.txt present sur le site (/.well-known/security.txt)

## Paiements (Stripe)
- [ ] Prix calcule cote serveur uniquement
- [ ] Webhooks verifient la signature Stripe
- [ ] Cles test ≠ cles live
- [ ] Cle secrete en variable d'environnement

## Infrastructure
- [ ] SSL/TLS valide (grade A sur ssllabs.com)
- [ ] HSTS active
- [ ] SPF + DKIM + DMARC configures
- [ ] Seuls ports 80/443 ouverts
- [ ] Header "Server" ne revele pas la version

## Legal / RGPD
- [ ] Banner cookies avec option de refus
- [ ] Politique de confidentialite a jour
- [ ] Suppression de compte possible
- [ ] Export de donnees possible
- [ ] Liste des sous-traitants (Stripe, Supabase, etc.)
- [ ] Contact vie privee accessible

## Dependances
- [ ] `npm audit` sans vulnerabilite critique/haute
- [ ] Pas de package non maintenu (>1 an sans update)
- [ ] Dependabot active sur GitHub

## Monitoring
- [ ] Alertes si le site tombe
- [ ] Logs d'erreurs actifs (pas en clair dans la console)
- [ ] Plan de reponse incident documente

---

## Score minimum : tous les points coches avant la mise en production.
