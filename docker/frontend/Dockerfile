# docker/frontend/Dockerfile
FROM node:20

WORKDIR /app

# Copier uniquement package.json et package-lock.json
COPY ./frontend/package*.json ./

# Installer les dépendances propres à Linux
RUN npm ci --legacy-peer-deps

# Copier tout le code
COPY ./frontend /app

# Installer vite globalement pour éviter les problèmes
RUN npm install -g vite

# Exposer le port
EXPOSE 5173

# Lancer Vite
CMD ["npm", "run", "dev"]
