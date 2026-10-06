# CLAUDE.md — Configuration de reference

Copier dans `~/.claude/CLAUDE.md` et adapter a ton profil (voir `02-build/skills-guide/skills-install.md` section 4 pour la commande qui sauvegarde ton CLAUDE.md actuel avant).

Ce fichier est lu par Claude au debut de chaque session. Plus il est long, plus il coute de tokens a chaque message : garde-le sous 100 lignes.

---

## Qui je suis

<!-- Remplis en 3 lignes : metier, stack, ce que tu veux obtenir. Exemple : -->
<!-- Freelance web, Next.js + Supabase, je livre des sites vitrines a des PME. -->
<!-- Objectif : livrer vite et propre, chaque livrable doit aider a vendre. -->

## Abonnement et budget tokens

<!-- Garde la ligne qui te correspond, supprime l'autre. -->
- Abonnement **Pro** (Sonnet) : pas de sous-agents en parallele sauf si je le demande, prefere `/gsd-quick` et `/gsd-fast` au workflow GSD complet, propose `/compact` quand le contexte depasse 50 %.
- Abonnement **Max** : sous-agents autorises quand la tache est vraiment parallele.

---

## Structure meta-prompt (appliquer pour tout prompt complexe)

```
CONTEXTE       — qui je suis, secteur, chiffres cles
TACHE          — ce que le prompt doit produire
EXEMPLE OUTPUT — exemple formate du resultat attendu
CONTRAINTES    — ce qui est interdit (reponses vagues, generalites, "ca depend")
CRITERES       — comment savoir si la reponse est bonne
UTILISATION    — l'action concrete declenchee par le resultat
```

---

## Templates reutilisables

Dossier : `~/.claude/templates/`
- `dark-light-toggle.md` — Dark/light mode complet (Next.js + Tailwind + HTML pur)

## Prompts experts

Dossier : `~/.claude/prompts/` (copie des piliers du kit, voir skills-install.md section 4)
- `01-launch/brand-launch-prompts.md` — 10 prompts lancement de marque
- `04-grow/acquisition/acquisition-prompts.md` — 10 prompts acquisition clients
- `04-grow/content/instagram/workflow-complet.md` — Pipeline 5 etapes croissance Instagram
- `04-grow/content/faceless-video/pipeline-court-format.md` — 7 prompts chaines contenu court format
- `05-scale/business-strategy-prompts.md` — 10 meta-prompts BCG
- `03-protect/audit-prompts/security-audit-prompts.md` — prompts audit securite
- `03-protect/checklists/security-checklist.md` — checklist avant mise en production

Pour utiliser : lire le fichier prompt et appliquer la structure au contexte du projet.

---

## Principes de travail (tous projets)

- **Contexte** : viser 50 % de contexte utilise, ne jamais depasser 70 %. Au-dela, relancer dans une nouvelle session.
- **Decisions verrouillees** : une fois une decision prise (fichier `.planning/STATE.md` si tu utilises GSD, sinon une section « Decisions » de ce fichier), ne pas la remettre en question plus tard.
- **Tranches verticales** : une feature complete (donnees + API + interface) a la fois, jamais couche par couche.
- **Chaque verification = une commande** : « ca marche » doit etre prouve par une commande qui vient de tourner (test, build, curl), pas par une lecture du code.
- **Specs = resultats attendus** : decrire quoi verifier, pas comment construire.
- **Jamais « c'est fait » sans preuve fraiche** : commande de verification lancee juste avant.
- **Test d'abord quand c'est possible** : si tu peux ecrire `expect(fonction(entree)).toBe(sortie)`, ecris le test avant le code (logique metier, API, calculs). Pas de test pour le CSS, la mise en page ou la config.
- **Jamais de correction sans cause racine** : comprendre pourquoi ca casse avant de corriger.

---

## Securite

- Jamais de cle, token ou mot de passe en clair dans un fichier versionne. Utiliser `.env.local` (ignore par git) ou le gestionnaire de secrets de la plateforme.
- Jamais de `git push --force`, jamais de `rm -rf` sur un chemin qui n'a pas ete affiche juste avant.
- Jamais de deploiement en production sans build frais qui passe.
- Avant d'installer un skill ou un plugin : ouvrir son `SKILL.md` et verifier la source (voir skills-install.md).

---

## Techniques de prompting avancees

**Pipeline chaining** — output prompt N = input prompt N+1 :
`[NICHE] > [TOPIC] > [IDEA] > [ANGLE] > [HOOK] > [SCRIPT] > [DRAFT]`

**Decision forcee** — eliminer toutes les options sauf une a chaque etape.

**Boucle autonome (Max uniquement, jamais sur Pro)** — pour une feature bien scopee avec des tests solides, on peut relancer Claude en boucle sur un `PROMPT.md`. Toujours avec une limite d'iterations et une condition d'arret, sinon la boucle vide ton quota :
```bash
for i in $(seq 1 10); do
  claude -p "$(cat PROMPT.md)" --max-turns 30 || break
  npm test && break      # condition d'arret : les tests passent
done
```
Fichiers : `PROMPT.md` (la tache) + `AGENTS.md` (60 lignes max de regles) + `specs/` (resultats attendus seulement).
