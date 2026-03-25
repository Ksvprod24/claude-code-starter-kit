# Lancement de Marque — 10 prompts sequentiels

Pipeline complet pour creer et lancer une marque de zero. Chaque prompt elimine toutes les options sauf une.

```
Pipeline sequentiel :
Prompt 01 (Naming) → Prompt 02 (Positionnement) → Prompt 03 (Identite visuelle)
  → Prompt 04 (Voix) → Prompt 05 (Tagline) → Prompt 06 (Landing page)
  → Prompt 07 (Plan J-14 a J+7) → Prompt 08 (Posts) → Prompt 09 (Emails)
  → Prompt 10 (Brand story)
```

---

## Prompt 01 — Naming (trouver le nom parfait)

```
CONTEXTE : Mon projet est [DESCRIPTION_PROJET]. Mon audience cible est [AUDIENCE].
Les valeurs que je veux transmettre sont [VALEURS]. Mes concurrents s'appellent [NOMS_CONCURRENTS].

TACHE : Genere 5 noms de marque uniques. Pour chaque nom :
- Verifie que le .com / .fr est probablement disponible (pas de mot generique)
- Score de memorabilite /10 + justification
- Score de differenciation vs concurrents /10
Recommande LE meilleur avec justification.

EXEMPLE OUTPUT :
1. [NOM] — .com dispo probable — Memorabilite: 8/10 — Differenciation: 9/10
>> RECOMMANDATION : [NOM] car [raison decisive]

CONTRAINTES : Pas de noms generiques. Pas de jeux de mots forces. Max 3 syllabes.
CRITERES DE SUCCES : Je peux verifier la disponibilite du domaine dans les 5 minutes.
UTILISATION : Acheter le nom de domaine aujourd'hui.
```

---

## Prompt 02 — Positionnement (une phrase qui vend)

```
CONTEXTE : Ma marque est [NOM]. Mon produit/service est [DESCRIPTION].
Mon client ideal est [CLIENT_IDEAL]. Mes concurrents se positionnent ainsi : [POSITIONNEMENTS_CONCURRENTS].

TACHE : Ecris UNE phrase de positionnement de max 15 mots qui :
- Dit ce que je fais
- Dit pour qui
- Dit en quoi c'est different
Donne 3 versions, score chacune, recommande la meilleure.

EXEMPLE OUTPUT :
1. "[PHRASE_15_MOTS]" — Clarte: 9/10 — Differenciation: 8/10
2. "[PHRASE_15_MOTS]" — Clarte: 7/10 — Differenciation: 9/10
3. "[PHRASE_15_MOTS]" — Clarte: 8/10 — Differenciation: 7/10
>> RECOMMANDATION : Version 1 car [raison]

CONTRAINTES : Max 15 mots. Pas de jargon. Un enfant de 10 ans doit comprendre.
CRITERES DE SUCCES : La phrase tient sur une bio Instagram/LinkedIn.
UTILISATION : Reecrire tous mes profils et ma page d'accueil.
```

---

## Prompt 03 — Identite visuelle (brief design)

```
CONTEXTE : Ma marque est [NOM]. Mon positionnement est [PHRASE_POSITIONNEMENT].
Mon audience est [AUDIENCE]. Le ton est [SERIEUX/DECONTRACTE/PREMIUM/ACCESSIBLE].

TACHE : Produis un brief identite visuelle complet :
1. Palette de couleurs — 1 primaire + 1 secondaire + 1 accent + 1 neutre (codes hex)
2. Typographie — 1 font titres + 1 font corps (Google Fonts uniquement)
3. Style visuel — 3 mots-cles qui definissent l'esthetique
4. Mood — 3 marques de reference dont s'inspirer (pas concurrents directs)
5. Logo direction — forme, style, ce qu'il doit evoquer

CONTRAINTES : Couleurs en hex. Fonts disponibles sur Google Fonts uniquement.
CRITERES DE SUCCES : Un designer peut executer le logo avec ce brief seul.
UTILISATION : Briefer un designer ou generer avec IA.
```

---

## Prompt 04 — Voix et ton de marque

```
CONTEXTE : Ma marque est [NOM]. Mon positionnement est [PHRASE].
Mon audience a [AGE] ans, est [DESCRIPTION_PSYCHO].

TACHE : Definis la voix de marque :
1. Personnalite — Si la marque etait une personne, qui serait-elle ?
2. Ton — 4 adjectifs (ex: direct, chaleureux, expert, decomplexe)
3. Vocabulaire — 10 mots/expressions a utiliser tout le temps
4. Anti-vocabulaire — 10 mots/expressions INTERDITS
5. Exemple — Reecris cette phrase standard de 3 manieres differentes dans ta voix :
   "Nous aidons les entreprises a se developper"

CONTRAINTES : La voix doit etre reconnaissable sans voir le logo.
CRITERES DE SUCCES : Quelqu'un peut ecrire un post pour ma marque sans me demander.
UTILISATION : Document de reference pour tout le contenu futur.
```

---

## Prompt 05 — Tagline (slogan)

```
CONTEXTE : Ma marque est [NOM]. Positionnement : [PHRASE].
Voix : [4_ADJECTIFS_TON]. Mon audience veut [DESIR_PROFOND].

TACHE : Ecris 5 taglines. Pour chaque :
- Score impact emotionnel /10
- Score memorabilite /10
- Test : est-ce qu'elle fonctionne seule sans contexte ? (oui/non)
Recommande LA meilleure.

CONTRAINTES : Max 7 mots. Pas de cliche ("votre succes, notre mission"). Pas de jeux de mots.
CRITERES DE SUCCES : Je peux la mettre sur une carte de visite.
UTILISATION : Header du site + bio reseaux + signature email.
```

---

## Prompt 06 — Landing page copy (pre-lancement)

```
CONTEXTE : Ma marque est [NOM]. Tagline : [TAGLINE].
Le lancement est dans [X] jours. Mon offre est [DESCRIPTION_OFFRE].

TACHE : Ecris le contenu complet d'une landing page pre-lancement :
1. Hero — Titre + sous-titre + CTA (call-to-action)
2. Probleme — 3 douleurs de mon audience
3. Solution — Ce que ma marque change
4. Social proof — Placeholder pour temoignages/chiffres
5. CTA final — Formulaire email ou pre-commande

CONTRAINTES : Chaque section max 3 phrases. CTA avec verbe d'action.
CRITERES DE SUCCES : Je peux copier-coller dans mon site en 20 minutes.
UTILISATION : Creer la page avec un builder ou Next.js.
```

---

## Prompt 07 — Plan de lancement jour par jour (J-14 a J+7)

```
CONTEXTE : Ma marque est [NOM]. Date de lancement : [DATE].
Budget marketing : [BUDGET]. Canaux disponibles : [CANAUX] (Instagram, email, LinkedIn, etc.)

TACHE : Cree un plan de lancement detaille :
- J-14 a J-7 : Teasing / build anticipation
- J-7 a J-1 : Montee en puissance
- J-Day : Actions du jour de lancement
- J+1 a J+7 : Suivi post-lancement

Pour chaque jour : action + canal + contenu a publier + objectif mesurable.

CONTRAINTES : Max 2 actions par jour (realiste pour un solo entrepreneur).
CRITERES DE SUCCES : Je peux suivre le plan sans reflechir chaque matin.
UTILISATION : Calendrier de lancement a imprimer.
```

---

## Prompt 08 — Contenu reseaux sociaux (10 posts)

```
CONTEXTE : Ma marque est [NOM]. Voix : [4_ADJECTIFS]. Tagline : [TAGLINE].
Lancement dans [X] jours.

TACHE : Ecris 10 posts pour le lancement :
- 3 posts teasing (curiosite)
- 3 posts education (le probleme que je resous)
- 2 posts storytelling (mon histoire / pourquoi j'ai cree ca)
- 1 post lancement (annonce officielle)
- 1 post social proof (temoignage / resultat)

Chaque post : accroche stop-scroll + corps + CTA + hashtags.

CONTRAINTES : Chaque accroche max 10 mots. Pas de emojis dans les accroches.
CRITERES DE SUCCES : Je peux planifier les 10 posts en une session.
UTILISATION : Programmer dans Later/Buffer/manuellement.
```

---

## Prompt 09 — Email de lancement

```
CONTEXTE : Ma marque est [NOM]. Mon offre : [OFFRE].
J'ai [X] emails dans ma liste. Mon objectif : [OBJECTIF_LANCEMENT].

TACHE : Ecris 3 emails :
1. Email J-3 : Teasing — creer l'attente
2. Email J-Day : Lancement — annonce + CTA principal
3. Email J+2 : Relance — urgence / derniere chance

Chaque email : objet (max 50 car) + preview text + corps + CTA.

CONTRAINTES : Chaque email lisible en 60 secondes. Un seul CTA par email.
CRITERES DE SUCCES : Taux d'ouverture vise > 30%. CTA clair et unique.
UTILISATION : Programmer dans Mailchimp/Resend/ConvertKit.
```

---

## Prompt 10 — Brand story (narratif fondateur)

```
CONTEXTE : Je suis [QUI]. J'ai cree [NOM] parce que [RAISON].
Mon parcours : [PARCOURS_COURT]. Le moment declencheur : [MOMENT_CLE].

TACHE : Ecris mon brand story en 3 formats :
1. Version longue (page A Propos) — 300 mots
2. Version moyenne (post LinkedIn) — 150 mots
3. Version courte (bio / pitch) — 50 mots

Structure : Avant (le probleme) > Le declic > Apres (la solution) > La mission.

CONTRAINTES : Pas de "je suis passionne par". Pas de CV. Du storytelling emotionnel.
CRITERES DE SUCCES : Quelqu'un qui lit la version courte veut lire la longue.
UTILISATION : Page A Propos + LinkedIn + presentations.
```

---

## Variables a remplacer

- `[NOM]` — nom de ta marque
- `[DESCRIPTION_PROJET]` — ce que fait le projet
- `[AUDIENCE]` / `[CLIENT_IDEAL]` — qui tu cibles
- `[VALEURS]` — ce que la marque represente
- `[NOMS_CONCURRENTS]` — noms des concurrents directs
- `[BUDGET]` — budget marketing disponible
- `[DATE]` — date de lancement prevue
- `[CANAUX]` — reseaux sociaux / canaux disponibles

## Ponts avec les autres piliers

- Prompt 02 (Positionnement) → alimente 04-grow/acquisition Prompt 02 (Cold Email) et Prompt 03 (LinkedIn)
- Prompt 03 (Identite visuelle) → alimente 02-build pour le design system du site
- Prompt 04 (Voix) → alimente 04-grow/content pour le ton des posts Instagram et faceless
- Prompt 06 (Landing page) → alimente 04-grow/acquisition Prompt 05 (Page de vente)
- Prompt 10 (Brand story) → alimente 05-scale Prompt 10 (Pitch investisseur)
