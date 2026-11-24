# SuperMarket – génération de l'APK Android

## Prérequis (une seule fois)
- Node.js 18+ : https://nodejs.org
- Android Studio (inclut le SDK Android et Java) : https://developer.android.com/studio

## Étapes
1. Ouvrir un terminal dans ce dossier, puis :
   npm install
   npx cap add android
   npx cap sync android
   npx cap open android
2. Dans Android Studio, attendre la fin de la synchronisation Gradle, puis :
   Build > Build Bundle(s) / APK(s) > Build APK(s)
3. L'APK se trouve dans :
   android/app/build/outputs/apk/debug/app-debug.apk
   Copier ce fichier sur le téléphone et l'installer (autoriser les sources inconnues).

## APK signé (Play Store / distribution)
Build > Generate Signed Bundle / APK > APK, créer un keystore et le conserver précieusement.

## Mettre à jour l'app
Modifier www/index.html, puis : npx cap sync android et reconstruire l'APK.

## Option sans Android Studio : GitHub (gratuit)
1. Créer un dépôt GitHub et y envoyer tout le contenu de ce dossier
   (y compris le dossier caché .github).
2. Onglet Actions > "Build APK Android" > Run workflow (ou simple push).
3. Quand c'est vert (environ 5 min), ouvrir l'exécution et télécharger
   l'artefact "supermarket-apk" : il contient app-debug.apk.
