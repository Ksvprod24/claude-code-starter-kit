# Claude Code Starter Kit

Kit complet pour transformer Claude Code en machine de guerre : skills, prompts experts, templates, et configuration optimisee.

## Ce que contient ce repo

### Prompts experts (3 packs)

| Pack | Fichier | Description |
|------|---------|-------------|
| **Business** | `prompts/business/meta-prompts-consultant.md` | 10 meta-prompts structures comme un consultant BCG — diagnostic croissance, audit prix, positionnement, SWOT, segmentation clients, simulation financiere, acquisition, audit ops, roadmap 90j, pitch investisseur |
| **Instagram** | `prompts/instagram/workflow-complet.md` | Pipeline 5 etapes : audit compte > calendrier 30j > accroches stop-scroll > rewriting storytelling > idees virales |
| **Faceless Video** | `prompts/faceless-video/pipeline-court-format.md` | Pipeline 7 prompts chaines pour contenu court format sans visage : niche > topic > idee > angle > hook > script > draft final. Decision forcee a chaque etape |

### Template

| Template | Fichier | Description |
|----------|---------|-------------|
| **Dark/Light Toggle** | `templates/dark-light-toggle.md` | Composant dark/light mode complet (Next.js + Tailwind + HTML pur) avec auto-detection jour/nuit, palette de classes, et composants prets a l'emploi |

### Configuration Claude Code

| Fichier | Description |
|---------|-------------|
| `CLAUDE.md` | Configuration de reference — principes agents, structure meta-prompt, workflow GSD, skills |
| `skills-install.md` | Guide d'installation des 15 skills + GSD |

## Installation rapide

### 1. Copier les prompts

```bash
# Creer le dossier prompts dans ta config Claude
mkdir -p ~/.claude/prompts/{instagram,business,faceless-video}
mkdir -p ~/.claude/templates

# Copier les fichiers
cp prompts/instagram/* ~/.claude/prompts/instagram/
cp prompts/business/* ~/.claude/prompts/business/
cp prompts/faceless-video/* ~/.claude/prompts/faceless-video/
cp templates/* ~/.claude/templates/
```

### 2. Installer les skills et GSD

Suis le guide dans `skills-install.md`.

### 3. Configurer CLAUDE.md

Copie `CLAUDE.md` dans `~/.claude/CLAUDE.md` et adapte-le a ton profil.

## Comment utiliser les prompts

Chaque pack de prompts est un pipeline : le resultat du prompt N sert d'input au prompt N+1.

**Business** — Ouvre le fichier, remplace les variables entre crochets `[ROLE]`, `[SECTEUR]`, `[CA]` etc. par tes infos, et envoie chaque prompt a Claude dans l'ordre.

**Instagram** — Meme principe. Variables : `[NICHE]`, `[CLIENT_IDEAL]`, `[PRODUIT]`.

**Faceless Video** — Lance le prompt 1, recupere le resultat, injecte-le dans le prompt 2, etc. Chaque etape elimine toutes les options sauf une.

## Structure meta-prompt (pour creer tes propres prompts)

```
CONTEXTE       — qui je suis, secteur, chiffres cles
TACHE          — ce que le prompt doit produire
EXEMPLE OUTPUT — exemple formate du resultat attendu
CONTRAINTES    — ce qui est interdit (reponses vagues, generalites, "ca depend")
CRITERES       — comment savoir si la reponse est bonne
UTILISATION    — l'action concrete declenchee par le resultat
```

Cette structure force l'IA a donner des reponses actionnables, pas du blabla.

## Liens utiles

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) — Documentation officielle
- [Superpowers Skills](https://github.com/jessesquires/claude-code-superpowers) — Skills workflow par Jesse Vincent
- [GSD (Get Shit Done)](https://github.com/gsd-framework/gsd) — Framework projet complet

---

Made with Claude Code.
