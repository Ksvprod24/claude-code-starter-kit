# Acquisition Clients — 10 prompts

Prompts pour trouver, convertir et garder des clients. Du premier contact au renouvellement.
Benchmarks integres (taux de reponse, conversion, etc.) bases sur des donnees 2025-2026.

```
Pipeline complet :
Prompt 01 (ICP) → Prompt 08 (SEO) + Prompt 04 (Lead Magnet)     ← INBOUND
Prompt 01 (ICP) → Prompt 02 (Cold Email) + Prompt 03 (LinkedIn)  ← OUTBOUND
Prompt 05 (Landing Page) + Prompt 09 (Pricing)                    ← CONVERSION
Prompt 06 (Objections)                                             ← VENTE
Prompt 10 (Onboarding) → Prompt 07 (Referral)                    ← RETENTION
```

---

## Prompt 01 — ICP Laser (Profil Client Ideal)

```
CONTEXTE : Je suis [ROLE] (ex: developpeur freelance + agence web).
Mes offres : [OFFRE_1 avec prix] | [OFFRE_2 avec prix] | [OFFRE_3 avec prix].
Mes 3 meilleurs clients : [NOM_1 secteur + CA genere + duree] | [NOM_2] | [NOM_3].
Mes 3 pires clients : [NOM_4 + pourquoi] | [NOM_5] | [NOM_6].

TACHE : Construis mon ICP sur 5 axes :
1. Firmographique — taille entreprise, secteur, CA, stack technique
2. Psychographique — frustrations, objectifs a 6 mois, declencheur d'achat
3. Comportemental — ou ils cherchent, comment ils achetent
4. Budget — fourchette realiste, qui signe le cheque, cycle de decision
5. Signaux d'achat — evenements detectables (levee de fonds, recrutement, refonte site)

EXEMPLE OUTPUT :
ICP : "Startup SaaS B2B, 5-20 pers, post-seed, qui lance son V2"
→ Frustration : [phrase verbatim du client ideal]
→ Declencheur : [evenement observable]
→ Canal : [ou le trouver]
→ Budget : [fourchette]
Anti-ICP : [profil a refuser systematiquement + pourquoi]

CONTRAINTES : UN seul ICP. Pas de "ca depend". L'anti-ICP est obligatoire.
Les signaux d'achat doivent etre verifiables sur LinkedIn/Crunchbase/Google Alerts.
CRITERES DE SUCCES : Je peux configurer une alerte automatique pour detecter mes prospects.
UTILISATION : Parametrer mes filtres LinkedIn Sales Navigator + Google Alerts cette semaine.
```

---

## Prompt 02 — Cold Email 3 touches

```
CONTEXTE : Mon ICP est [ICP_1_LIGNE].
Mon offre : [OFFRE + PRIX]. Mon differenciateur : [CE_QUI_ME_REND_UNIQUE].
Preuve sociale : [RESULTAT_CLIENT ou METRIQUE].

TACHE : Ecris une sequence de 3 cold emails espaces de J+0, J+3, J+7.
- Email 1 (J+0) : PAS (Problem-Agitate-Solve) — 80 mots max. Sujet : question.
- Email 2 (J+3) : Preuve sociale + insight — 60 mots max. Sujet : "re:" naturel.
- Email 3 (J+7) : Breakup email — 40 mots max. Donne de la valeur en partant.

Chaque email : sujet + corps + CTA unique (question fermee oui/non).

CONTRAINTES : Zero jargon marketing. Ton conversationnel.
Aucun email ne commence par "Je" ou "Bonjour, je suis".
Taux de reponse cible : >8% (benchmark 2025-2026 sequences personnalisees).
CRITERES DE SUCCES : Chargeable dans Instantly/Lemlist en 5 minutes.
UTILISATION : Lancer ma premiere campagne de 50 prospects cette semaine.
```

---

## Prompt 03 — Script LinkedIn DM (4 messages)

```
CONTEXTE : Mon ICP est [ICP]. Je cible des prospects qui [SIGNAL_OBSERVABLE]
(ex: viennent de poster sur X, ont change de poste, recrutent un dev).

TACHE : Ecris une sequence de 4 messages LinkedIn :
1. Demande de connexion (max 300 car) — pas de pitch, juste de la pertinence
2. Message J+1 post-connexion (max 3 lignes) — observation + question ouverte
3. Message J+5 valeur (max 5 lignes) — partage un insight utile SANS pitch
4. Message J+10 transition (max 4 lignes) — proposition legere de call 15 min

CONTRAINTES : Les mots "services" et "offre" sont INTERDITS avant le message 4.
Chaque message doit referencer quelque chose de SPECIFIQUE au prospect.
Pas de "j'adore votre travail".
CRITERES DE SUCCES : Taux d'acceptation >40%, taux de reponse >25%.
UTILISATION : 10 demandes de connexion qualifiees par jour ouvre.
```

---

## Prompt 04 — Lead Magnet qui qualifie

```
CONTEXTE : Mon ICP est [ICP]. Son probleme #1 est [PROBLEME].
Mon canal contenu : [CANAL] (LinkedIn/blog/YouTube/newsletter).
Mon offre payante : [OFFRE + PRIX].

TACHE : Concois UN lead magnet qui fait 3 choses :
1. Resout un micro-probleme en <15 minutes d'utilisation
2. Demontre mon expertise sans la donner entierement
3. Qualifie : celui qui le telecharge est proche d'acheter

Format : checklist | template Notion | calculateur | mini-audit | swipe file.
Justifie le choix en 1 phrase.

Inclus : titre accrocheur (max 10 mots) + contenu (3 bullet points) +
landing page copy (headline + subheadline + CTA) + lien logique vers offre payante.

CONTRAINTES : UN seul lead magnet. Pas de ebook 30 pages.
Creable en moins de 4 heures. Doit contenir un "moment aha" qui revele
un gap que seul ton service payant peut combler.
CRITERES DE SUCCES : Taux conversion landing page >25%.
UTILISATION : Creer et publier le lead magnet ce weekend.
```

---

## Prompt 05 — Page de vente (copy complete)

```
CONTEXTE : Mon offre est [DESCRIPTION]. Prix : [PRIX]. ICP : [ICP].
Resultat principal : [RESULTAT_MESURABLE]. Preuve : [TEMOIGNAGE ou METRIQUE].

TACHE : Ecris le copy complet en 9 sections :
1. HERO — Headline (max 10 mots) + Subheadline (max 20 mots) + CTA
2. PROBLEME — 3 douleurs specifiques (langage verbatim client)
3. AGITATION — Ce qui se passe si le probleme persiste (cout chiffre)
4. SOLUTION — 3 bullets "Ce que vous obtenez"
5. PREUVES — Temoignage + metrique + logos clients
6. COMMENT CA MARCHE — 3 etapes numerotees
7. PRIX — Ancrage (valeur percue vs prix reel)
8. FAQ — 4 objections transformees en arguments de vente
9. CTA FINAL — Urgence legitime + garantie + CTA

CONTRAINTES : Zero superlatif. Zero buzzword.
Chaque phrase doit survivre au test "et alors ?" — si le lecteur peut repondre "et alors ?", la phrase est trop vague.
Le CTA n'est JAMAIS "Contactez-nous" mais une action specifique.
CRITERES DE SUCCES : Copy envoyable tel quel a un integrateur.
UTILISATION : Mettre en ligne dans les 48h.
```

---

## Prompt 06 — Matrice Objections / Reponses

```
CONTEXTE : Mon offre est [DESCRIPTION + PRIX].
Les objections que j'entends : [OBJECTION_1] | [OBJECTION_2] | [OBJECTION_3].

TACHE : Matrice de 8 objections avec pour chacune :
1. L'objection verbatim (ce que le prospect dit)
2. L'objection reelle cachee (ce qu'il pense vraiment)
3. Reponse LAER en 2-3 phrases (Listen-Acknowledge-Explore-Respond)
4. Question de relance qui reprend le controle

Objections obligatoires :
- "C'est trop cher"
- "On va reflechir"
- "On a deja quelqu'un"
- "On peut le faire en interne"
- "Vous etes tout seul / trop petit"

CONTRAINTES : JAMAIS defensif. JAMAIS de "oui mais".
Ton de consultant confiant, pas de vendeur qui supplie.
Chaque reponse inclut un chiffre ou un exemple concret.
CRITERES DE SUCCES : Imprimable comme cheat sheet pour les calls.
UTILISATION : Preparer mes 3 prochains appels de vente.
```

---

## Prompt 07 — Programme de parrainage

```
CONTEXTE : Mon offre : [OFFRE + PRIX_MOYEN]. Clients satisfaits : [NOMBRE].
Panier moyen : [PANIER]. Outils : [OUTILS] (Notion, Stripe, email).

TACHE : Programme de referral avec :
1. Recompense — UN modele : commission cash | credit service | acces exclusif.
   Justifie en 1 phrase.
2. 3 moments precis ou demander un referral (quand + script exact)
3. Template message — email/DM pre-ecrit que le client forwarde a son contact
4. Tracking — comment suivre sans outil payant (Notion/spreadsheet)
5. Relance — rappel a J+30 et J+60

CONTRAINTES : Zero outil payant. Gerable en <30 min/semaine.
Premier referral possible dans les 14 jours.
CRITERES DE SUCCES : 20% des clients referent au moins 1 contact en 90 jours.
UTILISATION : Envoyer le premier message a mes 5 meilleurs clients cette semaine.
```

---

## Prompt 08 — Strategie SEO 90 jours

```
CONTEXTE : Mon expertise : [EXPERTISE]. Mon ICP : [ICP].
Mon site : [URL ou "pas encore de blog"]. Temps dispo : [HEURES]/semaine.

TACHE : Plan SEO 90 jours :
1. Pilier editorial — UN theme central (expertise × recherches Google de l'ICP)
2. Cluster 10 articles — titres + mot-cle cible + volume estime + difficulte
3. Calendrier publication — frequence realiste
4. Template article — structure H1/H2/H3 + longueur + CTA integre
5. Programmatic SEO — 1 idee de pages generees
   (ex: "[service] pour [ville]", "[outil] vs [outil]")
6. Distribution — recycler chaque article en 3 formats (LinkedIn, newsletter, thread)

CONTRAINTES : Mots-cles a intention transactionnelle/commerciale uniquement.
Chaque article contient un CTA vers le lead magnet ou l'offre.
Contenu d'autorite (E-E-A-T), pas de "top 10 outils" generique.
CRITERES DE SUCCES : Les 3 premiers articles publiables sans recherche supplementaire.
UTILISATION : Ecrire et publier le premier article cette semaine.
```

---

## Prompt 09 — Page de prix qui convertit

```
CONTEXTE : Mes offres : [OFFRE_1 + PRIX] | [OFFRE_2 + PRIX] | [OFFRE_3 + PRIX].
Mon ICP : [ICP]. Panier moyen : [PANIER]. Objectif : +[X]% panier moyen.

TACHE : Restructure ma grille en 3 tiers avec pricing psychology :
1. Ancre haute (premium) — fait paraitre le milieu raisonnable
2. Sweetspot (recommande) — 60% des clients doivent choisir ce tier
3. Entree — version reduite qui qualifie

Pour chaque tier :
- Nom parlant (pas "Basic/Pro/Enterprise")
- Prix + frequence (mensuel vs annuel, reduction 15-20%)
- 5-7 features par ordre de valeur percue
- Ce qui est EXCLU (pousse vers le tier superieur)
- Badge visuel ("Populaire", "Meilleur rapport qualite-prix")

Elements de conversion :
- Ancrage : "Valeur totale : [X]EUR — Votre prix : [Y]EUR"
- Garantie + social proof sous chaque tier
- Toggle mensuel/annuel (defaut = annuel)

CONTRAINTES : Ecart tier 1→2 : <2x. Ecart tier 2→3 : >2.5x (effet decoy).
3 tiers = 1.4x mieux que 2 tiers, 1.8x mieux que 4+.
CRITERES DE SUCCES : Difference entre les 3 tiers comprise en <10 secondes.
UTILISATION : Refaire ma page de prix et A/B tester dans les 7 jours.
```

---

## Prompt 10 — Onboarding + Upsell (7 touchpoints)

```
CONTEXTE : Mon offre : [OFFRE + PRIX]. Duree projet : [DUREE].
Process post-signature actuel : [DECRIRE ou "rien de structure"].
Offre complementaire : [UPSELL + PRIX].

TACHE : Sequence post-signature en 7 touchpoints :
1. J+0 — Email bienvenue : confirmation + prochaines etapes + quick win
2. J+1 — Questionnaire onboarding (5-7 questions max)
3. J+3 — Premier livrable partiel — creer le "moment aha" tot
4. J+7 — Check-in proactif : "Voici ou on en est"
5. Mi-projet — Rapport d'avancement + mention subtile upsell
6. Livraison — Email structure + demande temoignage (3 questions guidees)
7. J+30 post-livraison — Suivi + proposition upsell + demande referral

Pour chaque : sujet email + corps (copy exact, max 150 mots) + action requise.

CONTRAINTES : L'upsell ne doit jamais ressembler a du forcing.
La demande de temoignage inclut 3 questions guidees (pas "laissez un avis").
Sequence automatisable dans n'importe quel outil email.
CRITERES DE SUCCES : Zero question "et maintenant on fait quoi ?" du client.
UTILISATION : Configurer la sequence et l'appliquer a mon prochain client.
```

---

## Variables a remplacer

- `[ICP]` — profil client ideal (resultat du Prompt 01)
- `[OFFRE]` — ton produit/service principal
- `[PRIX]` — tarif de l'offre
- `[RESULTAT_MESURABLE]` — ce que le client obtient concretement
- `[SIGNAL_OBSERVABLE]` — evenement detectable chez le prospect
- `[CANAL]` — ou tu publies du contenu
- `[EXPERTISE]` — ton domaine d'expertise

## Ponts avec les autres piliers

- 05-scale Prompt 02 (Audit prix) → alimente Prompt 09 (Page de prix)
- 05-scale Prompt 03 (Positionnement) → alimente le differenciateur dans Prompt 02 (Cold Email)
- 05-scale Prompt 04 (Clients rentables) → alimente l'anti-ICP dans Prompt 01
- 01-launch Prompt 02 (Positionnement) → alimente tous les prompts acquisition
