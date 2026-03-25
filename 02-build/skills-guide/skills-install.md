# Installation des Skills et GSD

## Pre-requis

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) installe
- Node.js 18+
- Git

---

## 1. Skills Superpowers (Jesse Vincent) — 14 skills workflow

Ces skills s'activent automatiquement selon le contexte (debug, feature, review, etc.).

### Installation

```bash
# Cloner le repo des skills
git clone https://github.com/jessesquires/claude-code-superpowers.git /tmp/superpowers

# Copier les skills dans ta config Claude
mkdir -p ~/.claude/skills
cp -r /tmp/superpowers/skills/* ~/.claude/skills/

# Nettoyer
rm -rf /tmp/superpowers
```

### Skills inclus

| Skill | Quand il s'active | Ce qu'il fait |
|-------|-------------------|---------------|
| `brainstorming` | Avant toute implementation | Design > spec > review > approval > code |
| `writing-plans` | Feature a implementer | Plan granulaire (2-5min/etape, TDD integre) |
| `executing-plans` | Plan approuve | Execution structuree avec checkpoints |
| `subagent-driven-development` | Taches independantes | Coordonne plusieurs agents en parallele |
| `dispatching-parallel-agents` | 3+ failures | Un agent par probleme, en parallele |
| `systematic-debugging` | Bug ou test failure | Root Cause > Pattern > Hypothesis > Fix |
| `test-driven-development` | Toute feature ou bugfix | RED-GREEN-REFACTOR strict |
| `verification-before-completion` | Avant de dire "c'est fait" | Commande de verification obligatoire |
| `receiving-code-review` | Review recue | Verifie avant d'implementer |
| `requesting-code-review` | Apres implementation | Dispatch reviewer subagent |
| `using-git-worktrees` | Isolation necessaire | Worktree avec setup auto |
| `finishing-a-development-branch` | Implementation terminee | 4 options : merge, PR, keep, discard |
| `writing-skills` | Creer un nouveau skill | TDD applique a la doc process |
| `using-superpowers` | Toujours | Invoque le bon skill avant d'agir |

---

## 2. UI/UX Pro Max — Intelligence design

```bash
# Cloner et installer
git clone https://github.com/pimmsaas/ui-ux-pro-max.git ~/.claude/skills/ui-ux-pro-max
```

Base de donnees : 67 styles, 161 palettes, 57 typographies, 99 guidelines UX, 13 stacks.

### Utilisation

```bash
# Recherche design system
python3 ~/.claude/skills/ui-ux-pro-max/scripts/search.py "saas dashboard" --design-system

# Par domaine
python3 ~/.claude/skills/ui-ux-pro-max/scripts/search.py "keyword" --domain style

# Par stack
python3 ~/.claude/skills/ui-ux-pro-max/scripts/search.py "keyword" --stack nextjs
```

---

## 3. GSD (Get Shit Done) — Framework projet complet

57 commandes slash, 18 agents specialises, 5 hooks de securite.

### Installation

```bash
# Installer GSD
claude /gsd:update
```

### Commandes principales

```bash
# Nouveau projet complet
/gsd:new-project

# Workflow phase par phase
/gsd:discuss-phase 1    # Capture preferences
/gsd:plan-phase 1       # Plan detaille
/gsd:execute-phase 1    # Execution atomique
/gsd:verify-work 1      # Verification
/gsd:ship               # PR + livraison

# Taches rapides
/gsd:quick "description"  # Tache ad-hoc
/gsd:fast "description"   # Encore plus rapide
/gsd:debug "symptome"     # Debug methodique
```

---

## 4. Configuration recommandee

Copie le `CLAUDE.md` de ce repo dans `~/.claude/CLAUDE.md` pour avoir tous les principes agents actives.
