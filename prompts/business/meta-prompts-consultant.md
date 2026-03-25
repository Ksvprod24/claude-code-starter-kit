# Meta-Prompts Business — Structure Consultant BCG

## Architecture universelle (à appliquer à tous ces prompts)

```
CONTEXTE : [qui tu es, ton secteur, tes chiffres clés]
TACHE : [ce que le prompt doit produire]
EXEMPLE OUTPUT : [exemple formaté du résultat attendu]
CONTRAINTES : [ce qui est interdit — réponses vagues, généralités, etc.]
CRITERES DE SUCCES : [comment savoir si la réponse est bonne]
UTILISATION : [l'action concrète que tu vas faire avec le résultat]
```

---

## Prompt 01 — Diagnostiquer les 3 freins à la croissance

```
CONTEXTE : Je suis [ROLE] dans [SECTEUR]. Mon CA actuel est [CA].
Mon principal problème est [PROBLEME].

TACHE : Identifie mes 3 freins principaux à la croissance avec une analyse root cause.
Adopte le cadre d'un consultant BCG.

EXEMPLE OUTPUT :
Frein 1 : [Nom] — Impact estimé : [X]€/mois — Action immédiate : [action]
Frein 2 : [Nom] — Impact estimé : [X]€/mois — Action immédiate : [action]
Frein 3 : [Nom] — Impact estimé : [X]€/mois — Action immédiate : [action]

CONTRAINTES : Pas de généralités. Chaque frein doit être nommé précisément et chiffré.
CRITERES DE SUCCES : Je dois pouvoir agir sur chaque frein cette semaine.
UTILISATION : Prioriser mon agenda des 7 prochains jours.
```

---

## Prompt 02 — Audit prix / sous-vente

```
CONTEXTE : Mon offre est [DESCRIPTION_OFFRE]. Je facture [PRIX_ACTUEL].
Mes concurrents facturent [PRIX_CONCURRENTS].

TACHE : Détermine si je me sous-vends, avec % de preuve et 3 preuves concrètes.
Donne 2 actions concrètes : augmenter les prix OU créer une offre premium.

EXEMPLE OUTPUT :
Sous-vente estimée : X% — Preuve 1 / Preuve 2 / Preuve 3
Recommandation : [augmentation prix OU offre premium] — Justification

CONTRAINTES : Pas de "ça dépend". Une seule recommandation claire avec chiffres.
CRITERES DE SUCCES : Je sais exactement quoi changer dans ma grille tarifaire.
UTILISATION : Réviser ma page de vente cette semaine.
```

---

## Prompt 03 — Audit positionnement vs concurrents

```
CONTEXTE : Je suis [POSITIONNEMENT_ACTUEL]. Mes 3 concurrents directs sont [C1], [C2], [C3].

TACHE : Compare mon positionnement aux 3 concurrents.
Identifie ma vulnérabilité, ma force, et un différenciateur exploitable.

OUTPUT : Mon positionnement reformulé en une phrase unique.

CONTRAINTES : La phrase finale doit être différente de celle de mes concurrents.
CRITERES DE SUCCES : La phrase peut tenir sur ma bio Instagram/LinkedIn.
UTILISATION : Réécrire tous mes profils et ma page d'accueil.
```

---

## Prompt 04 — Clients rentables vs à éliminer

```
CONTEXTE : Voici mon portefeuille clients : [LISTE_CLIENTS_avec_CA_et_heures_passées]

TACHE : Segmente en 3 groupes : Garder/Développer | Surveiller | Éliminer.
Critères par segment + estimation des heures libérées si j'élimine le segment 3.

CONTRAINTES : Chaque client doit être dans exactement un groupe. Pas de "peut-être".
CRITERES DE SUCCES : Je sais exactement qui ne pas renouveler.
UTILISATION : Décisions de renouvellement contrats ce trimestre.
```

---

## Prompt 05 — SWOT actionnel chiffré

```
CONTEXTE : [DESCRIPTION_BUSINESS] — CA : [CA] — Équipe : [TAILLE]

TACHE : Construis un SWOT transformé en plan d'action priorisé.
Chaque quadrant → actions avec timeline et impact CA estimé.

OUTPUT :
- Cette semaine : [actions]
- Ce trimestre : [actions]

CONTRAINTES : Chaque action doit avoir un impact CA estimé en €.
CRITERES DE SUCCES : Le SWOT se transforme en todo list concrète.
```

---

## Prompt 06 — Simulateur 3 scénarios financiers

```
CONTEXTE : Je dois choisir entre : [OPTION_A] | [OPTION_B] | [OPTION_C]
Mon cash actuel : [CASH]. Mes charges fixes : [CHARGES]/mois.

TACHE : Modélise le cash flow à 30/60/90 jours pour chaque scénario.
Recommande le scénario avec le meilleur ratio profit/risque.

OUTPUT : Tableau 3x3 (scénarios × horizons) + une recommandation unique avec justification.

CONTRAINTES : Une seule recommandation finale. Chiffres obligatoires.
```

---

## Prompt 07 — Nouveau canal d'acquisition

```
CONTEXTE : Budget : [BUDGET]/mois. Temps disponible : [HEURES]/semaine.
Secteur : [SECTEUR]. Ce que j'ai déjà testé : [CANAUX_TESTÉS].

TACHE : Recommande UN canal d'acquisition adapté à mon profil.
Plan test 30 jours avec indicateurs mesurables.

CONTRAINTES : Un seul canal. Pas de liste. Plan concret, pas de théorie.
CRITERES DE SUCCES : Je peux commencer demain matin.
```

---

## Prompt 08 — Audit inefficacités opérationnelles

```
CONTEXTE : Voici mes tâches hebdomadaires et le temps passé : [LISTE_TACHES_TEMPS]
Mon taux horaire est [TAUX_HORAIRE]€/h.

TACHE : Détecte les 3-5 inefficacités qui me coûtent le plus.
Pour chaque : temps perdu/mois + coût réel + cause racine.

OUTPUT : Liste priorisée + heures/mois récupérées si résolu.

CONTRAINTES : Chiffres obligatoires. Pas de recommandations génériques.
```

---

## Prompt 09 — Roadmap 90 jours

```
CONTEXTE : Mon objectif principal est [OBJECTIF] d'ici [DATE].
Ressources : [RESSOURCES]. Contraintes : [CONTRAINTES].

TACHE : Construis un roadmap semaine par semaine avec objectifs SMART,
jalons intermédiaires, et un point de décision critique (continuer Y ou pivoter vers Z).

OUTPUT : Document de référence une page.

CRITERES DE SUCCES : Je peux l'imprimer et le coller sur mon bureau.
```

---

## Prompt 10 — Pitch investisseur / associé

```
CONTEXTE : Mon projet est [DESCRIPTION]. Traction actuelle : [MÉTRIQUES].
Je cherche [MONTANT ou TYPE_ASSOCIÉ] pour [USAGE].

TACHE : Construis un script de pitch 10 minutes en 6 blocs :
Hook | Problème | Solution | Traction | Ask | Gestion des objections

OUTPUT : Script complet + guide de répétition.

CONTRAINTES : Le hook doit tenir en une phrase. Chaque bloc max 90 secondes.
CRITERES DE SUCCES : Je peux le réciter sans notes après 3 répétitions.
```
