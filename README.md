# Adhan

App installable (PWA) : horaires de prière calculés sur l'appareil, appel sonore, position GPS, boussole Qibla en direct, mode hors ligne.

## Contenu

- `index.html` : toute l'app
- `manifest.webmanifest`, `sw.js`, `icons/` : installation et hors ligne
- `adhan.mp3` (à ajouter, facultatif) : si ce fichier est posé à côté de `index.html`, l'app le propose comme son d'appel

## Mettre en ligne

Le GPS, la boussole et l'installation exigent une adresse en **HTTPS**. Un fichier ouvert depuis le téléphone ne suffit pas.

Déposez le contenu de ce dossier sur un hébergement statique gratuit (GitHub Pages, Netlify, Cloudflare Pages ou équivalent), à la racine du site ou dans un sous-dossier.

## Installer sur le téléphone

- **Android (Chrome)** : ouvrez l'adresse, puis « Installer l'app » (bouton dans l'app ou menu du navigateur).
- **iPhone (Safari)** : bouton Partager, puis « Sur l'écran d'accueil ». Les notifications ne marchent qu'une fois l'app ajoutée.

Au premier lancement : touchez le repère à côté de la ville pour utiliser votre position, puis « Activer les appels », puis « Activer la boussole » (iPhone demande l'accès « Mouvement et orientation »).

## Limites à connaître

- Une app web ne peut pas planifier de son quand elle est fermée ou l'écran verrouillé. L'appel retentit seulement si l'app est ouverte (écran allumé conseillé : option « Garder l'écran allumé »). Pour sonner téléphone verrouillé, il faut une app native (voir plus bas).
- La boussole lit le nord magnétique, à quelques degrés près. Tenez le téléphone à plat, loin des aimants et des métaux.
- Les horaires dépendent de la méthode choisie. Comparez avec votre mosquée et utilisez les décalages en minutes.
- Les polices viennent de Google Fonts en ligne, puis restent en cache. Sans connexion au premier lancement, l'app utilise les polices du système.

## Mettre à jour

Après avoir modifié un fichier, changez `CACHE` en haut de `sw.js` (par exemple `adhan-v2`) pour que les téléphones rechargent les fichiers.

## Passer en app native (notifications téléphone verrouillé)

Le plus direct est d'emballer ce dossier avec Capacitor et son plugin de notifications locales, qui sait programmer un son à l'heure exacte même app fermée. Cela demande un ordinateur avec Android Studio (APK) ou Xcode et un compte développeur Apple (iPhone).
