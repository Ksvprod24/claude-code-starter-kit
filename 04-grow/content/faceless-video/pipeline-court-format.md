# Pipeline Faceless Content — 7 prompts en chaine

Pipeline sequentiel pour creer du contenu court format sans presence personnelle.
Chaque prompt prend l'OUTPUT du precedent comme INPUT.

```
[NICHE] → [TOPIC] → [IDEA] → [ANGLE] → [HOOK] → [SCRIPT] → [DRAFT publie]
```

---

## Prompt 1 — Direction du jour (Daily Direction Lock)

```
Act as a senior content strategist.
Define one clear posting direction for the niche [NICHE].
The direction must remove guessing completely
and be strong enough to guide daily posts without variation or rethinking.
```
OUTPUT → utilise le resultat comme [TOPIC] dans le prompt suivant

---

## Prompt 2 — Decision du sujet (Topic Decision Authority)

```
Act as an editorial lead.
Decide the single best topic to post today from this topic space [TOPIC].
Eliminate all other options and return only one topic worth publishing now.
```
OUTPUT → utilise le resultat comme [IDEA] dans le prompt suivant

---

## Prompt 3 — Engagement sur une idee (Idea Commitment Point)

```
Act as a content editor.
Select one specific idea from this idea pool [IDEA].
Discard alternatives and commit to the idea that should be executed immediately without hesitation.
```
OUTPUT → utilise le resultat comme [ANGLE] dans le prompt suivant

---

## Prompt 4 — Angle sans visage (Faceless Angle Lock)

```
Act as a positioning specialist.
Commit to one clear angle for this idea [ANGLE]
that performs without personal presence, storytelling, or face-led content.
The angle must stand on clarity alone.
```
OUTPUT → utilise le resultat comme [HOOK] dans le prompt suivant

---

## Prompt 5 — Accroche de controle (Hook Control Line)

```
Act as a hook specialist.
Write one definitive opening hook from this hook concept [HOOK].
The hook must stop scrolling immediately
without relying on trends, shock, or exaggeration.
```
OUTPUT → utilise le resultat comme [HOOK] dans le prompt suivant

---

## Prompt 6 — Script (Script Momentum Build)

```
Act as a short-form content writer.
Write a complete short-form script starting from this hook [HOOK].
Remove setup, filler, and explanation.
Maintain forward momentum until the final line.
```
OUTPUT → utilise le resultat comme [DRAFT] dans le prompt suivant

---

## Prompt 7 — Validation finale (Publish Readiness Check)

```
Act as a senior editor.
Rewrite this draft [PASTE DRAFT] into a final, publish-ready version.
Remove uncertainty, tighten language,
and confirm the post performs one clear job with no revision needed.
```

---

## Technique cle
Chaque prompt **elimine toutes les options sauf une**. Pas de listes, pas de "peut-etre".
Decision forcee a chaque etape → zero paralysie d'analyse.
