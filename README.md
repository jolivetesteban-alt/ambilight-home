# Ambilight Home – launcher Android TV

Écran d'accueil personnalisé pour TV Philips Google TV / Android TV :
fond lumineux animé façon Ambilight, heure et date, et toutes tes applications installées.
Navigation à la télécommande (flèches + OK).

## Compiler

1. Installe **Android Studio** (version récente) sur ton ordinateur.
2. Ouvre le dossier `AmbilightHome` (File > Open).
3. Laisse Gradle se synchroniser (connexion internet nécessaire la première fois).
4. Build > Build APK(s) : l'APK est créé dans `app/build/outputs/apk/debug/`.

## Installer sur la TV

1. Sur la TV : Paramètres > Système > À propos > clique 7 fois sur « Build » pour activer le mode développeur.
2. Paramètres > Système > Options pour les développeurs > active « Débogage USB » (ou « Débogage réseau »).
3. Trouve l'adresse IP de la TV (Paramètres > Réseau).
4. Sur ton ordinateur :

```
adb connect IP_DE_LA_TV:5555
adb install app/build/outputs/apk/debug/app-debug.apk
```

Autre option : copie l'APK sur une clé USB et installe-le avec une app de fichiers.

## L'utiliser comme écran d'accueil

Lance « Ambilight Home » depuis la liste des apps pour la tester.

Sur beaucoup de Google TV, la touche Accueil continue d'ouvrir le launcher d'origine,
car Google ne permet pas toujours de le remplacer. Si ta TV propose le choix,
sélectionne Ambilight Home quand le système te le demande.
Sinon, tu peux la lancer à la main ou l'associer à un bouton avec une app de remappage.

## Personnaliser

Tout est dans `app/src/main/java/com/example/ambilighthome/MainActivity.kt` :
- couleurs du halo : liste `colors` dans `AmbilightBackground`
- vitesse de l'animation : `durationMillis`
- taille des tuiles : `AppTile`
