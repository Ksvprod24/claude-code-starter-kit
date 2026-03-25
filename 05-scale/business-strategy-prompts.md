# Strategie Business — 10 meta-prompts BCG

Prompts structures comme un consultant BCG. Chaque prompt force des chiffres et une decision claire. Zero "ca depend".

---

## Architecture universelle (a appliquer a tous ces prompts)

```
CONTEXTE : [qui tu es, ton secteur, tes chiffres cles]
TACHE : [ce que le prompt doit produire]
EXEMPLE OUTPUT : [exemple formate du resultat attendu]
CONTRAINTES : [ce qui est interdit — reponses vagues, generalites, etc.]
CRITERES DE SUCCES : [comment savoir si la reponse est bonne]
UTILISATION : [l'action concrete que tu vas faire avec le resultat]
```

---

## Prompt 01 — Diagnostiquer les 3 freins a la croissance

```
CONTEXTE : Je suis [ROLE] dans [SECTEUR]. Mon CA actuel est [CA].
Mon principal probleme est [PROBLEME].

TACHE : Identifie mes 3 freins principaux a la croissance avec une analyse root cause.
Adopte le cadre d'un consultant BCG.

EXEMPLE OUTPUT :
Frein 1 : [Nom] — Impact estime : [X]€/mois — Action immediate : [action]
Frein 2 : [Nom] — Impact estime : [X]€/mois — Action immediate : [action]
Frein 3 : [Nom] — Impact estime : [X]€/mois — Action immediate : [action]

CONTRAINTES : Pas de generalites. Chaque frein doit etre nomme precisement et chiffre.
CRITERES DE SUCCES : Je dois pouvoir agir sur chaque frein cette semaine.
UTILISATION : Prioriser mon agenda des 7 prochains jours.
```

---

## Prompt 02 — Audit prix / sous-vente

```
CONTEXTE : Mon offre est [DESCRIPTION_OFFRE]. Je facture [PRIX_ACTUEL].
Mes concurrents facturent [PRIX_CONCURRENTS].

TACHE : Determine si je me sous-vends, avec % de preuve et 3 preuves concretes.
Donne 2 actions concretes : augmenter les prix OU creer une offre premium.

EXEMPLE OUTPUT :
Sous-vente estimee : X% — Preuve 1 / Preuve 2 / Preuve 3
Recommandation : [augmentation prix OU offre premium] — Justification

CONTRAINTES : Pas de "ca depend". Une seule recommandation claire avec chiffres.
CRITERES DE SUCCES : Je sais exactement quoi changer dans ma grille tarifaire.
UTILISATION : Reviser ma page de vente cette semaine.
```

---

## Prompt 03 — Audit positionnement vs concurrents

```
CONTEXTE : Je suis [POSITIONNEMENT_ACTUEL]. Mes 3 concurrents directs sont [C1], [C2], [C3].

TACHE : Compare mon positionnement aux 3 concurrents.
Identifie ma vulnerabilite, ma force, et un differenciateur exploitable.

OUTPUT : Mon positionnement reformule en une phrase unique.

CONTRAINTES : La phrase finale doit etre differente de celle de mes concurrents.
CRITERES DE SUCCES : La phrase peut tenir sur ma bio Instagram/LinkedIn.
UTILISATION : Reecrire tous mes profils et ma page d'accueil.
```

---

## Prompt 04 — Clients rentables vs a eliminer

```
CONTEXTE : Voici mon portefeuille clients : [LISTE_CLIENTS_avec_CA_et_heures_passees]

TACHE : Segmente en 3 groupes : Garder/Developper | Surveiller | Eliminer.
Criteres par segment + estimation des heures liberees si j'elimine le segment 3.

CONTRAINTES : Chaque client doit etre dans exactement un groupe. Pas de "peut-etre".
CRITERES DE SUCCES : Je sais exactement qui ne pas renouveler.
UTILISATION : Decisions de renouvellement contrats ce trimestre.
```

---

## Prompt 05 — SWOT actionnel chiffre

```
CONTEXTE : [DESCRIPTION_BUSINESS] — CA : [CA] — Equipe : [TAILLE]

TACHE : Construis un SWOT transforme en plan d'action priorise.
Chaque quadrant → actions avec timeline et impact CA estime.

OUTPUT :
- Cette semaine : [actions]
- Ce trimestre : [actions]

CONTRAINTES : Chaque action doit avoir un impact CA estime en €.
CRITERES DE SUCCES : Le SWOT se transforme en todo list concrete.
```

---

## Prompt 06 — Simulateur 3 scenarios financiers

```
CONTEXTE : Je dois choisir entre : [OPTION_A] | [OPTION_B] | [OPTION_C]
Mon cash actuel : [CASH]. Mes charges fixes : [CHARGES]/mois.

TACHE : Modelise le cash flow a 30/60/90 jours pour chaque scenario.
Recommande le scenario avec le meilleur ratio profit/risque.

OUTPUT : Tableau 3x3 (scenarios x horizons) + une recommandation unique avec justification.

CONTRAINTES : Une seule recommandation finale. Chiffres obligatoires.
```

---

## Prompt 07 — Nouveau canal d'acquisition

```
CONTEXTE : Budget : [BUDGET]/mois. Temps disponible : [HEURES]/semaine.
Secteur : [SECTEUR]. Ce que j'ai deja teste : [CANAUX_TESTES].

TACHE : Recommande UN canal d'acquisition adapte a mon profil.
Plan test 30 jours avec indicateurs mesurables.

CONTRAINTES : Un seul canal. Pas de liste. Plan concret, pas de theorie.
CRITERES DE SUCCES : Je peux commencer demain matin.
```

---

## Prompt 08 — Audit inefficacites operationnelles

```
CONTEXTE : Voici mes taches hebdomadaires et le temps passe : [LISTE_TACHES_TEMPS]
Mon taux horaire est [TAUX_HORAIRE]€/h.

TACHE : Detecte les 3-5 inefficacites qui me coutent le plus.
Pour chaque : temps perdu/mois + cout reel + cause racine.

OUTPUT : Liste priorisee + heures/mois recuperees si resolu.

CONTRAINTES : Chiffres obligatoires. Pas de recommandations generiques.
```

---

## Prompt 09 — Roadmap 90 jours

```
CONTEXTE : Mon objectif principal est [OBJECTIF] d'ici [DATE].
Ressources : [RESSOURCES]. Contraintes : [CONTRAINTES].

TACHE : Construis un roadmap semaine par semaine avec objectifs SMART,
jalons intermediaires, et un point de decision critique (continuer Y ou pivoter vers Z).

OUTPUT : Document de reference une page.

CRITERES DE SUCCES : Je peux l'imprimer et le coller sur mon bureau.
```

---

## Prompt 10 — Pitch investisseur / associe

```
CONTEXTE : Mon projet est [DESCRIPTION]. Traction actuelle : [METRIQUES].
Je cherche [MONTANT ou TYPE_ASSOCIE] pour [USAGE].

TACHE : Construis un script de pitch 10 minutes en 6 blocs :
Hook | Probleme | Solution | Traction | Ask | Gestion des objections

OUTPUT : Script complet + guide de repetition.

CONTRAINTES : Le hook doit tenir en une phrase. Chaque bloc max 90 secondes.
CRITERES DE SUCCES : Je peux le reciter sans notes apres 3 repetitions.
```

---

## Variables a remplacer

- `[ROLE]` — ton poste/role
- `[SECTEUR]` — ton marche
- `[CA]` — chiffre d'affaires actuel
- `[OFFRE]` — ton produit/service
- `[PRIX]` — tarif actuel
- `[BUDGET]` — budget disponible
- `[OBJECTIF]` — ce que tu veux atteindre
