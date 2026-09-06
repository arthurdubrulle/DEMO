# Site vitrine restaurant — démo

Page unique, sans dépendance ni build. Un seul fichier : `index.html`.

## Mettre en ligne sur GitHub Pages

1. Sur GitHub, **New repository** → nom au choix (ex. `demo-resto`) → **Public** → Create.
2. **Add file → Upload files** → déposer `index.html` (et ce README) → Commit.
3. **Settings → Pages** → Source : *Deploy from a branch* → Branch : `main`, dossier `/ (root)` → Save.
4. Au bout d'une à deux minutes, le site est sur `https://<ton-pseudo>.github.io/demo-resto/`.

En ligne de commande, si tu préfères :

```bash
cd site-resto
git init && git add . && git commit -m "Site vitrine restaurant"
git branch -M main
git remote add origin git@github.com:<ton-pseudo>/demo-resto.git
git push -u origin main
```

Puis activer Pages dans Settings comme ci-dessus.

## Ce qu'il faut changer pour un vrai client

| Où | Quoi |
|---|---|
| `<title>` et `<meta name="description">` | Nom réel + ville — c'est ce qui s'affiche dans Google |
| Bloc `application/ld+json` | Adresse, téléphone, horaires réels. Ce balisage alimente la fiche Google |
| Numéro `+590590000000` | Présent à quatre endroits (header, hero, infos, JSON-LD) |
| Ardoise du jour | Le seul bloc à mettre à jour souvent — c'est aussi ce qui fait revenir les gens |
| Liens Instagram / Facebook / Google | Actuellement `#` |
| Mention « Site de démonstration » | À retirer |
| Variables CSS `:root` | Palette : `--lagon`, `--sable`, `--safran`, `--roucou`, `--vert-madras` |

## Choix de conception

- **Pas de photo en hero.** Un restaurant sans photos professionnelles se dessert avec des images d'illustration génériques. Le hero met en avant l'ardoise du jour, qui est l'information réellement recherchée. Quand le client a de vraies photos, on les ajoute.
- **Le téléphone est le bouton principal.** En restauration indépendante, la réservation se fait au téléphone. Un formulaire ajoute une étape et une boîte mail à surveiller.
- **Section « à emporter, en direct ».** C'est l'argument de désintermédiation : commander sans passer par une plateforme à 30 % de commission.
- **Balisage `Restaurant` en JSON-LD.** Pour un restaurant, le référencement local pèse plus lourd que le site lui-même.

## Domaine personnalisé

GitHub Pages accepte un nom de domaine : ajouter un fichier `CNAME` contenant `www.ledomaine.fr`, puis pointer l'enregistrement DNS vers `<ton-pseudo>.github.io`. HTTPS est fourni gratuitement.
