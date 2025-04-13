# Trivia App - AWS Cloud Lab

Ce projet est une application complète utilisant AWS pour l'infrastructure backend et un frontend React hébergé sur Amazon S3.

## 🔧 Technologies utilisées

- AWS CloudShell
- AWS SAM (Serverless Application Model)
- AWS Lambda
- Amazon API Gateway
- Amazon DynamoDB
- AWS Step Functions
- Amazon S3 (hébergement statique)
- Git + GitHub
- React.js (frontend)
- Node.js v16 (via NVM)

## 🚀 Étapes de déploiement

1. Cloner le dépôt :
```bash
git clone https://github.com/FranceStan/trivia-app.git
cd trivia-app
```

2. Installer Node.js v16 avec NVM (si non présent) :
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
export NVM_DIR="$HOME/.nvm"
source "$NVM_DIR/nvm.sh"
nvm install 16
nvm use 16
```

3. Déployer le backend :
```bash
sam build
sam deploy --guided
```

4. Déployer le frontend :
```bash
cd front-end-react/
npm install
npm run build
aws s3 mb s3://<bucket-unique>
aws s3 sync --acl public-read build s3://<bucket-unique>/
```

5. Ouvrir dans le navigateur :
```
https://<bucket-unique>.s3.amazonaws.com/index.html
```

## 🧹 Nettoyage des ressources

```bash
sam delete
aws s3 rm s3://<bucket-name> --recursive
aws s3 rb s3://<bucket-name>
```

## 📦 Auteur

Projet réalisé dans le cadre d'un lab AWS pour la maîtrise du déploiement serverless et du cloud natif.
