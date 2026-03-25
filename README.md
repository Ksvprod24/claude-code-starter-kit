# Claude Code Starter Kit v2

Kit complet pour entrepreneurs et freelances qui utilisent Claude Code.
5 piliers, 42+ prompts, battle-tested sur 11+ projets reels.

```
LAUNCH → BUILD → PROTECT → GROW → SCALE
  ↑                                  |
  └──────────────────────────────────┘
```

---

## Les 5 piliers

### 01-launch/ — Creer et lancer une marque

10 prompts sequentiels : naming → positionnement → identite visuelle → voix de marque → tagline → landing page → plan de lancement J-14 a J+7 → posts reseaux → emails de lancement → brand story.

### 02-build/ — Configurer Claude Code + developper

- **CLAUDE.md** de reference — principes agents, structure meta-prompt, techniques avancees
- **Guide skills** — Installation des 15 skills (Superpowers + UI/UX Pro Max + GSD)
- **Templates** — Composants reutilisables (dark/light mode)

### 03-protect/ — Securiser au maximum

- **10 prompts d'audit** — OWASP Top 10, auth, API, Stripe, secrets, RGPD, serveur, incident
- **Guide pentesting** — Comment engager des hackers ethiques (freelance → plateforme → bug bounty)
- **Checklist** — 40+ points a verifier avant chaque mise en production

### 04-grow/ — Acquerir des clients + creer du contenu

- **10 prompts acquisition** — ICP, cold email, LinkedIn, lead magnet, page de vente, objections, parrainage, SEO, onboarding, retention
- **5 prompts Instagram** — Audit → calendrier 30j → accroches → storytelling → viral
- **7 prompts Faceless Video** — Pipeline decision forcee : niche → topic → idea → angle → hook → script → draft

### 05-scale/ — Strategie business

10 meta-prompts BCG : diagnostic croissance, audit prix, positionnement, segmentation clients, SWOT chiffre, simulation financiere, canal d'acquisition, audit ops, roadmap 90j, pitch investisseur.

---

## Installation rapide

```bash
# Cloner
git clone https://github.com/Ksvprod24/claude-code-starter-kit.git
cd claude-code-starter-kit

# Copier la config Claude Code
cp 02-build/claude-config/CLAUDE.md ~/.claude/CLAUDE.md

# Installer les skills (voir le guide)
cat 02-build/skills-guide/skills-install.md
```

## Comment utiliser les prompts

1. Ouvre le fichier du pilier qui t'interesse
2. Remplace les variables entre crochets `[VARIABLE]` par tes infos
3. Envoie chaque prompt a Claude dans l'ordre
4. Le resultat du prompt N sert d'input au prompt N+1

**Principe cle :** chaque prompt force UNE decision. Pas de listes de 10 options. Pas de "ca depend". Une seule recommandation actionnnable.

## Structure meta-prompt (pour creer tes propres prompts)

```
CONTEXTE       — qui je suis, secteur, chiffres cles
TACHE          — ce que le prompt doit produire
EXEMPLE OUTPUT — exemple formate du resultat attendu
CONTRAINTES    — ce qui est interdit (reponses vagues, generalites)
CRITERES       — comment savoir si la reponse est bonne
UTILISATION    — l'action concrete declenchee par le resultat
```

## Arborescence

```
claude-code-starter-kit/
├── 01-launch/
│   └── brand-launch-prompts.md        # 10 prompts lancement marque
├── 02-build/
│   ├── claude-config/
│   │   └── CLAUDE.md                  # Config de reference
│   ├── skills-guide/
│   │   └── skills-install.md          # Guide installation 15 skills + GSD
│   └── templates/
│       └── dark-light-toggle.md       # Template dark/light mode
├── 03-protect/
│   ├── audit-prompts/
│   │   └── security-audit-prompts.md  # 10 prompts audit securite
│   ├── pentesting-guide/
│   │   └── pentesting-guide.md        # Guide complet pentesting
│   └── checklists/
│       └── security-checklist.md      # 40+ points pre-deploy
├── 04-grow/
│   ├── acquisition/
│   │   └── acquisition-prompts.md     # 10 prompts acquisition
│   └── content/
│       ├── instagram/
│       │   └── workflow-complet.md    # 5 prompts Instagram
│       └── faceless-video/
│           └── pipeline-court-format.md # 7 prompts faceless
├── 05-scale/
│   └── business-strategy-prompts.md   # 10 meta-prompts BCG
└── README.md
```

## Liens utiles

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) — Documentation officielle
- [Superpowers Skills](https://github.com/jessesquires/claude-code-superpowers) — Skills workflow
- [GSD](https://github.com/gsd-framework/gsd) — Framework projet complet
- [UI/UX Pro Max](https://github.com/pimmsaas/ui-ux-pro-max) — Intelligence design

---

Cree par [@Ksvprod24](https://github.com/Ksvprod24) — battle-tested sur 11+ projets.
