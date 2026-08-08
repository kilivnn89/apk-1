# Maître de Maison — App Android (Espace Parent)

Coquille Android légère (Capacitor) qui affiche directement ton site déjà en
ligne (`maitre-de-maison-1.onrender.com/espace-parent-connexion.html`). Pas de
copie du contenu : l'app affiche toujours la dernière version de ton site.

GitHub Actions reconstruit l'APK automatiquement à chaque `git push` sur la
branche `main` — aucune installation locale (Android Studio, SDK...) n'est
nécessaire.

## Mettre en ligne sur GitHub

```bash
git init
git add .
git commit -m "Initial commit - app Android espace parent"
```

Crée le repo sur GitHub (comme pour `whatsapp-notifier`), puis :
```bash
git remote add origin https://github.com/<ton-user>/maitre-de-maison-app.git
git branch -M main
git push -u origin main
```

## Récupérer l'APK

1. Va sur ton repo GitHub → onglet **Actions**
2. Clique sur le workflow **"Build APK Android"** le plus récent (ça se lance
   automatiquement après le push, ça prend 3-5 minutes)
3. Une fois terminé (coche verte ✓), descends en bas de la page → section
   **Artifacts** → clique sur **maitre-de-maison-parent-apk** pour le
   télécharger (fichier `.zip` contenant le `.apk`)

## Installer l'APK sur un téléphone Android

1. Décompresse le `.zip`, tu obtiens `app-debug.apk`
2. Transfère-le sur le téléphone (par email, Google Drive, clé USB...)
3. Ouvre le fichier depuis le téléphone → Android va demander d'autoriser
   l'installation depuis une source inconnue (normal, c'est un APK "debug"
   non publié sur le Play Store) → autorise, installe

## Personnaliser

- **Nom de l'app / couleur d'écran de démarrage** : modifie `capacitor.config.json`
- **Icône de l'app** : à ajouter plus tard (nécessite des images à plusieurs
  tailles — dis-le si tu veux qu'on s'en occupe)
- **appId** (`com.maitredemaison.parent`) : identifiant unique de l'app,
  à garder stable une fois choisi (le changer = créer une "nouvelle" app aux
  yeux d'Android, les utilisateurs devraient réinstaller)

## Limite actuelle

Cette version produit un APK **debug non signé** — installable manuellement,
mais pas publiable sur le Google Play Store en l'état (il faut une version
"release" signée avec une clé, plus une inscription développeur Google payante
si tu veux publier sur le Store officiellement). Si tu veux publier sur le
Play Store plus tard, dis-le : c'est une étape en plus qu'on peut ajouter.
