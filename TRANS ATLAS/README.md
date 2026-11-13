# LOGIFLOW — prototype de démonstration

Prototype responsive inspiré de la maquette Figma, avec interface en français, données fictives crédibles et API FastAPI.

## Lancer sur son ordinateur

```bash
python -m venv .venv
# Windows : .venv\Scripts\activate
# macOS / Linux : source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

Ouvrir http://127.0.0.1:8000. L’API de démonstration est disponible sur `/api/health` et `/api/summary`.

## Mettre le projet sur GitHub

Créer un dépôt GitHub vide, puis depuis ce dossier :

```bash
git init
git add .
git commit -m "Créer le prototype LOGIFLOW"
git branch -M main
git remote add origin https://github.com/VOTRE-COMPTE/logiflow-demo.git
git push -u origin main
```

## Déploiement sur FastAPI Cloud avec GitHub

1. Depuis ce dossier, crée un dépôt GitHub et envoie le projet avec les commandes ci-dessus.
2. Ouvre le tableau de bord FastAPI Cloud, crée une application depuis **GitHub Repo**, puis connecte ton compte GitHub et sélectionne le dépôt.
3. Si tu as envoyé le contenu de ce dossier dans un sous-dossier du dépôt, indique ce sous-dossier comme **Root Directory**. Si tu as créé le dépôt directement à partir du contenu de `logiflow`, garde la racine par défaut.
4. FastAPI Cloud construit et déploie l’application. Les prochains commits poussés sur la branche par défaut déclenchent de nouveaux déploiements.

Tu peux aussi lancer le déploiement depuis un terminal après avoir envoyé le dépôt :

```bash
pip install "fastapi[standard]"
fastapi login
fastapi deploy
```

Le tableau de bord FastAPI Cloud demande de connecter un compte GitHub et un compte FastAPI Cloud. Ces étapes nécessitent tes identifiants personnels ; je n’ai pas connecté de comptes ni publié le projet depuis cet espace. La configuration du site et de l’API est réunie dans la même application.

## À savoir

Le prototype ne collecte aucun vrai document et ne gère pas de données personnelles réelles. Les données interactives de la maquette sont fictives et les changements restent dans le navigateur. La connexion, la base de données et les échanges réels avec transporteurs/paiements seront à construire dans les prochaines étapes.

Les aperçus documentaires sont des maquettes fictives structurées d’après les champs habituels des pièces de transport. La CMR reprend notamment les champs de l’expéditeur, du destinataire, du lieu et de la date de prise en charge, du lieu de livraison, de la nature et du poids des marchandises, ainsi que des frais et observations. Références : [modèle CMR de l’IRU](https://www.iru.org/resources/iru-library/iru-cmr-model-2007) et [guide e-CMR de l’UNECE](https://unece.org/trade/documents/2023/10/executive-guide-e-cmr).
