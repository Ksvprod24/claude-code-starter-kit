# CLAUDE.md — Configuration de reference

Copier dans `~/.claude/CLAUDE.md` et adapter a ton profil.

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

Dossier : `~/.claude/prompts/`
- `launch/brand-launch-prompts.md` — 10 prompts lancement de marque
- `grow/acquisition-prompts.md` — 10 prompts acquisition clients
- `grow/instagram/workflow-complet.md` — Pipeline 5 etapes croissance Instagram
- `grow/faceless-video/pipeline-court-format.md` — 7 prompts chaines contenu court format
- `scale/business-strategy-prompts.md` — 10 meta-prompts BCG
- `protect/security-audit-prompts.md` — 10 prompts audit securite

Pour utiliser : lire le fichier prompt et appliquer la structure au contexte du projet.

---

## Principes agents (tous projets)

- **50% contexte cible** — ne jamais depasser 70%, relancer dans nouveau contexte
- **STATE.md** — locker les decisions, agents downstream respectent sans re-questionner
- **Vertical slices** — feature complete (model+API+UI) par plan, jamais layer by layer
- **Nyquist Rule** — chaque verification = une commande automatisee
- **Specs = outcomes** — specifier quoi verifier, pas comment construire
- **Backpressure** — hooks + tests comme mecanismes de rejection durs
- **Iron Law verification** — jamais dire "c'est fait" sans commande de preuve fraiche
- **Iron Law TDD** — jamais de code prod sans test en echec d'abord
- **Iron Law debugging** — jamais de fix sans root cause investigation

---

## Techniques de prompting avancees

**Pipeline chaining** — output prompt N = input prompt N+1 :
`[NICHE] > [TOPIC] > [IDEA] > [ANGLE] > [HOOK] > [SCRIPT] > [DRAFT]`

**Decision forcee** — eliminer toutes les options sauf une a chaque etape

**Ralph Wiggum** — loop autonome pour features scopees + tests solides :
```bash
while :; do cat PROMPT.md | claude; done
```
Fichiers : PROMPT_build.md + PROMPT_plan.md + AGENTS.md (60 lignes max) + specs/ (outcomes only)
