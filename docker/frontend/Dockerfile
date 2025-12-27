FROM node:20-alpine

WORKDIR /app

# Copier uniquement les fichiers de dépendances
COPY ./frontend/package.json .

# Installer les dépendances Linux
RUN npm install

# Copier le reste du code
COPY ./frontend .

# Port du serveur Vite
EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host"]
