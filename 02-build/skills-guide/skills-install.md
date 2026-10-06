# Installation des Skills et GSD

## Avant de commencer : ton abonnement compte

| Abonnement | Modele par defaut | Ce que tu peux faire confortablement |
|---|---|---|
| **Pro** (~20 €/mois) | Sonnet, quota de 5 h glissantes | Prompts des piliers 01/03/04/05, skills simples, `/gsd-quick` et `/gsd-fast` |
| **Max** | Opus + Sonnet, quota 5x a 20x | Tout, y compris `/gsd-new-project` et les sous-agents en parallele |

Regles si tu es sur **Pro** :
- Commence par les prompts (un message = un resultat), pas par GSD complet.
- Evite tout ce qui lance plusieurs agents en parallele : chaque agent a son propre contexte et consomme ton quota separement.
- Lance `/compact` quand la barre de contexte depasse 50 %. Un contexte plein = reponses plus lentes, plus cheres, moins bonnes.
- Verifie ton quota avec `/usage` avant une grosse tache.

## Pre-requis

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) installe et connecte (`claude` dans un terminal, ou l'extension VS Code "Claude Code" d'Anthropic)
- Node.js 18+ (`node --version`)
- Git (`git --version`)
- **Windows** : utilise WSL (Ubuntu). Les commandes ci-dessous sont pour Mac / Linux / WSL.

## Regle de securite : d'ou viennent les skills

Un skill est un fichier d'instructions que Claude execute pour toi. Un skill malveillant peut lui faire lire tes fichiers, envoyer des donnees ou lancer des commandes.
- N'installe que depuis les trois sources officielles ci-dessous (verifiees le 2026-10-06).
- Ne fais jamais `git clone` d'un repo trouve dans un tweet ou un article sans ouvrir son `SKILL.md` avant.
- Si une commande d'install te demande `sudo` ou `curl ... | bash` depuis un site inconnu : stop.

---

## 1. Superpowers (Jesse Vincent / obra) — 14 skills workflow

Ces skills s'activent automatiquement selon le contexte (debug, feature, review, etc.).

### Installation (depuis Claude Code, pas depuis le terminal)

```
/plugin install superpowers@claude-plugins-official
```

C'est tout. Source officielle : https://github.com/obra/superpowers (marketplace Anthropic).

### Skills inclus

| Skill | Quand il s'active | Ce qu'il fait | Cout tokens |
|-------|-------------------|---------------|-------------|
| `using-superpowers` | Toujours | Invoque le bon skill avant d'agir | faible |
| `brainstorming` | Avant toute implementation | Design > spec > review > approval > code | faible |
| `writing-plans` | Feature a implementer | Plan granulaire (2-5 min/etape, TDD integre) | moyen |
| `executing-plans` | Plan approuve | Execution structuree avec checkpoints | moyen |
| `systematic-debugging` | Bug ou test failure | Root Cause > Pattern > Hypothesis > Fix | faible |
| `test-driven-development` | Toute feature ou bugfix | RED-GREEN-REFACTOR strict | faible |
| `verification-before-completion` | Avant de dire "c'est fait" | Commande de verification obligatoire | faible |
| `receiving-code-review` | Review recue | Verifie avant d'implementer | faible |
| `using-git-worktrees` | Isolation necessaire | Worktree avec setup auto | faible |
| `finishing-a-development-branch` | Implementation terminee | 4 options : merge, PR, keep, discard | faible |
| `writing-skills` | Creer un nouveau skill | TDD applique a la doc process | faible |
| `requesting-code-review` | Apres implementation | Lance un sous-agent reviewer | **eleve** |
| `subagent-driven-development` | Taches independantes | Plusieurs agents en parallele | **eleve** |
| `dispatching-parallel-agents` | 3+ failures | Un agent par probleme, en parallele | **eleve** |

Sur Pro : les 3 derniers videront ton quota vite. Dis a Claude "sans sous-agents" si tu veux les eviter.

---

## 2. UI/UX Pro Max — Intelligence design

Base de donnees : 67 styles, 96 palettes, 57 typographies, 99 guidelines UX, 13 stacks.

### Installation (au choix)

Option A, depuis Claude Code :
```
/plugin marketplace add nextlevelbuilder/ui-ux-pro-max-skill
/plugin install ui-ux-pro-max@ui-ux-pro-max-skill
```

Option B, depuis le terminal :
```bash
npm install -g ui-ux-pro-max-cli
uipro init --ai claude
```

Source officielle : https://github.com/nextlevelbuilder/ui-ux-pro-max-skill

### Utilisation

Le skill s'active tout seul des que tu demandes du design ("fais-moi une landing page", "ameliore ce dashboard"). Pas de commande Python a lancer a la main.

---

## 3. GSD Core (Get Shit Done) — Framework projet complet

Une centaine de commandes slash `/gsd-...`, agents specialises, hooks de suivi du contexte et de securite.

**Sur Pro, GSD est le plus gros consommateur de tokens de ce kit.** `/gsd-new-project` lance 4 agents de recherche en parallele. Commence par `/gsd-quick` et `/gsd-fast`, passe au workflow complet quand tu auras vu ce que ca coute.

### Installation (terminal)

```bash
npx @opengsd/gsd-core@latest --global --claude
```

Source officielle : https://github.com/open-gsd/gsd-core (paquet npm `@opengsd/gsd-core`). Attention : l'ancien paquet `get-shit-done-cc` est abandonne, ne l'installe pas.

Apres chaque mise a jour de GSD, ouvre `~/.claude/settings.json` et verifie que les hooks ajoutes te conviennent (l'installeur peut en rebrancher).

### Commandes principales

```bash
# Taches rapides (commence ici)
/gsd-fast "description"   # Trivial, inline, pas de sous-agent
/gsd-quick "description"  # Tache ad-hoc avec commit atomique
/gsd-debug "symptome"     # Debug methodique

# Workflow complet (Max, ou Pro avec un quota frais)
/gsd-new-project        # projet neuf
/gsd-onboard            # code existant
/gsd-discuss-phase 1    # Capture preferences
/gsd-plan-phase 1       # Plan detaille
/gsd-execute-phase 1    # Execution atomique
/gsd-verify-work 1      # Verification
/gsd-ship               # PR + livraison
/gsd-next               # perdu ? il te dit quoi faire ensuite
```

---

## 4. Configuration recommandee

Le `CLAUDE.md` de ce kit (`02-build/claude-config/CLAUDE.md`) contient les principes agents. **Ne remplace pas le tien si tu en as deja un** : sauvegarde d'abord, puis fusionne.

```bash
# Sauvegarde si un CLAUDE.md existe deja
[ -f ~/.claude/CLAUDE.md ] && cp ~/.claude/CLAUDE.md ~/.claude/CLAUDE.md.bak-$(date +%F)

# Copie le CLAUDE.md du kit + les prompts/templates qu'il reference
cp 02-build/claude-config/CLAUDE.md ~/.claude/CLAUDE.md
mkdir -p ~/.claude/templates ~/.claude/prompts
cp 02-build/templates/dark-light-toggle.md ~/.claude/templates/
cp -r 01-launch 03-protect 04-grow 05-scale ~/.claude/prompts/
```

## 5. Verifier que tout marche

Dans Claude Code :
```
/skills        # doit lister superpowers + ui-ux-pro-max
/gsd-help      # doit afficher l'aide GSD Core
/usage         # ton quota restant
```
