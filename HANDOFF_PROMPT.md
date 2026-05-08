# Prompt de passation pour une autre IA

Tu reprends un petit site statique déjà publié sur GitHub Pages.

## Contexte utilisateur

L'utilisateur veut une page mobile-friendly pour consulter un plan de nutrition sur 14 jours :

- Homme, 26 ans.
- Poids actuel : environ 113-115 kg.
- Objectif : 95 kg.
- Plan alimentaire : OMAD, One Meal A Day.
- Priorité : aliments à indice glycémique bas.
- Allergie : fruits de mer exclus, mais poisson autorisé.
- Besoin principal : une liste de repas sur deux semaines, alternatives possibles, liste de courses cochable, et indications de conservation/congélation.

## État actuel

Le site est déjà créé, versionné et publié.

- Dépôt GitHub : https://github.com/isayalony-ops/plan-omad-ig-bas
- Site public GitHub Pages : https://isayalony-ops.github.io/plan-omad-ig-bas/
- Branche : `main`
- Publication GitHub Pages : depuis la racine du dépôt, fichier `index.html`

## Fichiers importants

À fournir à l'autre IA ou à conserver dans le projet :

- `index.html` : fichier principal servi par GitHub Pages. Il contient tout : HTML, CSS et JavaScript inline.
- `omad-ig-bas-14-jours.html` : copie locale nommée du même site, gardée pour ouverture directe dans le navigateur.
- `README.md` : courte description du projet.
- `.gitignore` : ignore `phone-access-server.js`.

Fichier local optionnel :

- `phone-access-server.js` : petit serveur Node local pour accéder au site depuis un téléphone sur le même Wi-Fi. Il est ignoré par Git et ne doit pas être publié sauf demande explicite.

Il n'y a pas de fichiers `.css` ou `.js` séparés nécessaires au site public : le CSS et le JavaScript sont intégrés dans `index.html`.

## Fonctionnalités actuelles

Le site contient :

- Navigation sticky avec onglets : Courses, Guide, Jour 1 à Jour 14.
- Page d'introduction avec statistiques : objectif 95 kg, calories, protéines, fibres.
- Liste de courses cochable avec sauvegarde locale via `localStorage`.
- Badges de conservation dans la liste de courses :
  - `Congèle` : aliments à portionner et congeler.
  - `Cuit OK` : aliments à congeler après cuisson.
  - `Frais` : à garder au frigo, congélation déconseillée.
  - `Placard` : pas besoin de froid.
- Guide IG bas rapide.
- 14 repas OMAD avec calories, protéines, glucides, lipides, fibres.
- Alternatives par repas.
- Design responsive mobile.

## Contraintes à respecter

- Garder `index.html` comme source principale de GitHub Pages.
- Si `index.html` est modifié, synchroniser aussi `omad-ig-bas-14-jours.html` avec la même version.
- Ne pas ajouter de fruits de mer : crustacés et mollusques restent exclus.
- Le poisson est autorisé.
- Préserver l'approche IG bas : lentilles, pois chiches, haricots, quinoa, sarrasin, orge, pâtes complètes al dente, fruits rouges, pommes, agrumes.
- Éviter d'ajouter des aliments à IG haut comme pain blanc, riz blanc, jus, miel, céréales soufflées, biscuits, sauf mention explicite comme exception.
- Garder l'interface lisible sur mobile.
- Ne pas casser la persistance des cases cochées.

## Commandes utiles

Vérifier l'état Git :

```powershell
git status --short
```

Copier la version principale vers la version locale nommée :

```powershell
Copy-Item -LiteralPath "index.html" -Destination "omad-ig-bas-14-jours.html" -Force
```

Publier les modifications :

```powershell
git add README.md index.html omad-ig-bas-14-jours.html
git commit -m "Description courte du changement"
git push
```

Vérifier GitHub Pages :

```powershell
& "C:\Program Files\GitHub CLI\gh.exe" run list --repo isayalony-ops/plan-omad-ig-bas --limit 3
```

Vérifier que le site public répond :

```powershell
Invoke-WebRequest -Uri "https://isayalony-ops.github.io/plan-omad-ig-bas/" -UseBasicParsing
```

## Demande typique à reprendre

Continue à améliorer le site statique `Plan OMAD IG bas` en modifiant principalement `index.html`, puis synchronise `omad-ig-bas-14-jours.html`, commit et push sur GitHub. Respecte les contraintes nutritionnelles, la compatibilité mobile, GitHub Pages, et conserve la structure actuelle sauf si une amélioration demandée justifie un changement.
