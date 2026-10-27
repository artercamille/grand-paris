# Le Grand Paris

Jeu de propriétés en 3D sur un plateau aux rues de Paris, à jouer entre potes, en local sur un PC ou en ligne.

**Jouer :** https://artercamille.github.io/grand-paris/

## Fonctionnement

- Tout le jeu tient dans `index.html` (three.js depuis cdnjs/jsdelivr, polices intégrées).
- **Connexion Discord** : OAuth2 en flux implicite (scope `identify`), sans serveur. Le jeu récupère le pseudo et la photo de profil Discord et les garde dans le navigateur.
- **Jeu en ligne** : WebRTC pair à pair via PeerJS (`vendor/peerjs.min.js`, serveur de mise en relation public `0.peerjs.com`). L'hôte du salon fait autorité sur l'état de la partie ; les autres lui envoient leurs actions.
- Une invitation est un lien `…/grand-paris/#join=CODE`.

## Configurer Discord

1. https://discord.com/developers/applications → **New Application** → nomme-la « Le Grand Paris ».
2. Onglet **OAuth2** → **Redirects** → ajoute exactement `https://artercamille.github.io/grand-paris/` → **Save**.
3. Copie l'**Application ID** (onglet General Information) dans `config.js`.

## Sons et musique (`audio/`)

Musique jouée en direct par le jeu (séquenceur Web Audio) à partir d'échantillons d'instruments ; bruitages mixés en couches.

- Instruments (piano, harmonium, contrebasse, guitare, trompette, tuba, xylophone) : [tonejs-instruments](https://github.com/nbrosowsky/tonejs-instruments) par Nicholaus Brosowsky, licence **CC-BY 3.0**.
- Batterie, caisse enregistreuse, cloche, porte, souffles, vinyle : échantillons de [Sonic Pi](https://github.com/sonic-pi-net/sonic-pi) (Freesound, **CC0**).
- Chocs de dés (plastique, feutre, bois) : [dice-box](https://github.com/3d-dice/dice-box), licence **MIT**.
- Sons d'interface : [uisfx](https://www.npmjs.com/package/uisfx), **CC0**.

Les fichiers sont réencodés en MP3 mono 64 kb/s par `snd/mkaudio.py` (non publié).
