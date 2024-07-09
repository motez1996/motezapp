# Étape de build
FROM node:14 as build

# Définir le répertoire de travail dans le conteneur
WORKDIR /app

# Copier les fichiers package.json et package-lock.json
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier les fichiers du projet dans le conteneur
COPY . .

# Build de l'application Angular
RUN npm run build --prod

# Étape de production
FROM nginx:latest

# Copier les fichiers build du frontend dans le serveur Nginx
COPY --from=build /app/dist/front /usr/share/nginx/html

# Exposer le port 80
EXPOSE 80

# Commande par défaut pour démarrer Nginx
CMD ["nginx", "-g", "daemon off;"]
