# LEGAL-TODO — DAKOO, Korean street food

> **Ne pas mettre en ligne avant d'avoir traité la section 1.**
> État au 17 juillet 2026. Aucune donnée n'a été inventée : tout ce qui n'a pas pu être
> vérifié à une source est marqué `[à fournir]` et apparaît **en surbrillance rose sur le
> site lui-même**, exprès — pour qu'un trou se voie au lieu de se combler avec une
> supposition.

---

## 1. Bloquant avant la mise en ligne

### 1.1 Identité de l'éditeur (`mentions-legales.html`)

| Donnée | État |
|---|---|
| Capital social | **manquant** — obligatoire pour une SARL, ne figure dans aucun registre public |
| RCS | **à confirmer** — « RCS Nantes 902 013 911 » est la forme attendue, non vérifiée à une source |
| Directeur de la publication | **manquant** — la société a **deux gérants** (Thibault Gentric, Yeongun Gentric (Ku)) : lequel des deux assume la fonction ? |
| E-mail | **manquant** — apparaît dans les mentions légales, la confidentialité et le bloc accessibilité |
| Nom d'usage de la cogérante | **à confirmer** — voir § 2, le registre est ambigu |

Le téléphone (**02 72 02 15 96**) est repris du site existant : il est déjà renseigné partout.

### 1.2 Hébergeur (article 6 III-1 LCEN — obligatoire)

Nom, adresse, téléphone et site de l'hébergeur. **Aucun hébergeur définitif n'est arrêté**,
donc les quatre champs sont vides dans `mentions-legales.html`, et la durée de conservation
des journaux de connexion est vide dans `confidentialite.html`.

Une fois l'hébergeur retenu, vérifier s'il implique un **transfert hors UE** (section
correspondante de `confidentialite.html`).

> Le dossier contient un `.vercel/project.json` (projet `dakoo-site`) : le site est
> aujourd'hui **déployé via Vercel**. C'est un indice, **pas** une réponse : l'hébergeur à
> déclarer est celui qui servira le site en production, et sa raison sociale exacte, son
> adresse postale et son téléphone doivent être repris de sa documentation officielle.
> Rien n'a été rempli à sa place.

### 1.3 Photographies — aucun crédit

**Les 18 photos du site ne portent aucun crédit** (fichiers `assets/IMG_52xx`, noms d'appareil
bruts). L'auteur est inconnu et n'a pas pu être déduit :

- **qui a pris ces photos ?** → `[auteur des photographies à fournir]` dans les mentions légales ;
- **quelle cession de droits ?** support, durée, territoire → `[à confirmer]` ;
- **droit à l'image** : plusieurs clichés montrent des personnes reconnaissables (cliente près
  de la vitrine, terrasse, salle). Leur autorisation écrite doit exister.

### 1.4 Vérifier avant publication

```bash
grep -rn "à fournir\|à confirmer" *.html    # ne doit plus rien renvoyer
```

---

## 2. Ce qui a été vérifié (et n'est donc pas à redemander)

Relevé le **17 juillet 2026** au registre national des entreprises via l'API publique
`recherche-entreprises.api.gouv.fr` :

- Dénomination : **DAKOO**
- Forme : **SARL** (code INSEE 5499 — société à responsabilité limitée)
- Siège : **17 rue Bon Secours, 44000 Nantes**
- SIREN : **902 013 911** · SIRET siège : **902 013 911 00018**
- TVA : **FR56902013911**
- APE : **56.10C — Restauration de type rapide**
- Immatriculation : **26 juillet 2021**
- Gérants : **Thibault Gentric**, **Yeongun Gentric (Ku)**
- Coordonnées GPS du siège : **47.21343903, -1.553218201**
- État administratif : **actif**

Le siège social et l'établissement sont à la **même adresse** : il n'y a pas lieu de
distinguer les deux sur la page.

> **Anomalie du registre — deux gérants, trois entrées.** Le registre liste *trois*
> dirigeants, mais deux désignent la même personne, saisie sous deux formes différentes :
> « GENTRIC (KU) YEONGUN » et « KU (YEONGUN) GENTRIC ». La société a donc **deux gérants**,
> pas trois. Reste à trancher la forme exacte du nom d'usage de la cogérante — « Yeongun
> Gentric », « Yeongun Ku » ou « Yeongun Gentric née Ku ». Le site raconte que « Ku » est le
> nom de famille de Yeongun ; le registre la rattache à « Gentric ». Le doute est signalé sur
> la page, il n'a pas été tranché à la place du client.

> **Deux dates, pas une contradiction.** Le registre donne le **26 juillet 2021**
> (immatriculation de la société) ; le site annonce une ouverture **en novembre 2021**. Les
> deux peuvent être vraies — on immatricule avant d'ouvrir. Aucune des deux n'a été corrigée.

---

## 3. Pages légales : ce qui a été créé, et ce qui ne l'a pas été

### Créées

| Page | Pourquoi |
|---|---|
| `mentions-legales.html` | Obligatoire (art. 6 III LCEN) pour tout site édité par une société. |
| `confidentialite.html` | Transparence RGPD sur les journaux de l'hébergeur et les liens sortants, même sans collecte. Contient la section cookies (ancre `#cookies`). |

Rubrique : **« Le bas du ticket »** — le ticket de caisse est déjà l'objet signature de la
maquette (section Infos). Les pages légales en sont la suite logique : les pointillés de la
carte servent de fiche d'identité, l'astérisque du bandeau défilant sert de séparateur, la
numérotation continue en `( 05 )` et `( 06 )` après les quatre sections de l'accueil.

### Volontairement non créées

| Page | Pourquoi pas |
|---|---|
| **CGV** | Ce site ne vend rien et n'encaisse rien. Les boutons « Commander » sont des liens `tel:`. Aucun contrat n'est conclu par son intermédiaire : une CGV serait un document sans objet. Aucune CGV existante n'a été trouvée par ailleurs. |
| **CGU** | Aucun compte, aucun contenu déposé par l'utilisateur, aucun service interactif. Sans objet. |
| **Droit de rétractation** | Pas de vente à distance depuis ce site. |
| **Bannière de consentement cookies** | Voir § 4. |
| **`sitemap.xml`** | Voir § 5 — le domaine n'est pas connu, et il n'a pas été inventé. |

---

## 4. Cookies, traceurs, données

### Ce que le site fait réellement — mesuré le 17 juillet 2026 dans Chrome

Mesure faite sur les trois pages servies en local, via
`performance.getEntriesByType('resource')` :

| | index | mentions-legales | confidentialite |
|---|---|---|---|
| Cookies déposés | **aucun** | **aucun** | **aucun** |
| `localStorage` / `sessionStorage` | **0 / 0** | **0 / 0** | **0 / 0** |
| Requêtes vers des tiers | **aucune** | **aucune** | **aucune** |
| Ressources chargées | 27 | 10 | 8 |

Mesure aussi vérifiée : **aucun** formulaire, **aucun** compte utilisateur, **aucune**
newsletter, **aucun** paiement, **aucune** mesure d'audience, **aucune** iframe.

### Ce qui sort du site, et qui ne sort pas

- **Liens sortants uniquement** : Google Maps (« Itinéraire » + adresse du pied de page),
  Instagram, Facebook. Aucune carte, aucun widget, aucun embed : **rien n'est chargé depuis
  ces services tant que l'utilisateur ne clique pas.** C'est un choix, il faut le tenir.
- **Uber Eats et Naofood sont cités mais pas liés** — ce sont de simples `<span>` dans la
  section Infos. Aucune requête, aucun traceur. Si un jour on veut les rendre cliquables,
  un lien sortant suffit : **ne pas intégrer leurs modules.**
- Les boutons « Commander » sont des liens `tel:` — pas de commande en ligne.

### Pourquoi il n'y a pas de bannière

L'article 82 de la loi Informatique et Libertés impose le consentement **avant tout dépôt de
cookie non strictement nécessaire**. Aucun cookie n'étant déposé, il n'y a rien à consentir.
Une bannière serait une gêne sans objet. C'est un choix argumenté, pas un oubli.

**Ce qui déclencherait l'obligation d'en poser une :**

- ajouter Google Analytics, Matomo (en mode non exempté), un pixel Meta ou tout traceur ;
- **intégrer une carte Google Maps en `<iframe>`** (aujourd'hui l'itinéraire est un simple
  lien sortant, exprès) ;
- **intégrer un module Uber Eats / Naofood** dans les pages ;
- intégrer une vidéo, un widget Instagram ou Facebook ;
- **recharger les polices depuis Google Fonts** — voir ci-dessous.

Dans ces cas : dispositif Refuser / Accepter / Personnaliser, refus aussi simple que
l'acceptation, aucun dépôt avant consentement, lien permanent de modification du choix dans
le pied de page.

### Polices — ce qui a changé le 17 juillet 2026

Le site chargeait **Bricolage Grotesque, Black Han Sans, Instrument Serif, Instrument Sans et
Noto Sans KR depuis les serveurs de Google Fonts**. Chaque visite transmettait donc l'adresse
IP du visiteur à Google, sans consentement — le point précis sur lequel la CNIL et plusieurs
autorités européennes ont sanctionné des éditeurs.

Les cinq familles sont désormais **auto-hébergées** dans `assets/font/` (licence **SIL Open
Font License 1.1** pour les cinq — copyright et URL de licence conservés dans les fichiers,
`nameID` 0 et 14). **13 fichiers, 240 Ko au total.** Les `<link>` vers Google ont été retirés
de toutes les pages et les `@font-face` posés en tête de `styles.css`.

> **Le CSS a été sorti d'`index.html`.** Il était en ligne dans un `<style>` ; il est
> maintenant dans **`styles.css`**, à l'identique (aucune règle modifiée), pour être partagé
> avec les pages légales. Le rendu de l'accueil est inchangé — vérifié par capture.

**Latin** : sous-ensembles `latin` + `latin-ext` d'origine, repris tels quels de Google.
Une règle par famille/style/sous-ensemble, avec la plage de graisse réelle du fichier :
Instrument Sans normal est **variable 400–700** (un seul fichier couvre 400/500/600/700),
Bricolage Grotesque est variable sur l'axe `opsz` 12–96 à graisse 800 figée, le reste est
statique.

**Coréen — attention avant d'ajouter du texte en hangul.** Google découpe Black Han Sans et
Noto Sans KR en **327 fragments** (plus de 12 Mo de TTF source). Ils ont été **réduits aux
70 caractères hangul réellement présents dans les trois pages**, plus le latin et la
ponctuation dont ils ont besoin pour les légendes mixtes (« 핫도그 — corn dog », « 맛있게
드세요 — merci, à bientôt ! ») : **51 Ko au lieu de 12 Mo.**

> **Si vous ajoutez du texte coréen sur le site, il faut régénérer ces trois fichiers**,
> sinon les nouveaux caractères s'afficheront dans une police de repli. Procédure :
>
> ```bash
> # 1. récupérer les TTF complets (UA neutre = Google sert la police entière)
> curl -s 'https://fonts.googleapis.com/css2?family=Black+Han+Sans&family=Noto+Sans+KR:wght@400;700'
> # 2. relever les caractères hangul de tous les .html, puis pour chaque police :
> python3 -m fontTools.subset SOURCE.ttf \
>   --text="<tous les caractères hangul du site>" \
>   --unicodes='U+0020-007E,U+00A0-00FF,U+2000-206F,U+20AC' \
>   --layout-features='*' --name-IDs='*' \
>   --flavor=woff2 --output-file=assets/font/CIBLE.woff2
> ```

Deux constats sans conséquence, notés pour mémoire :

- **Black Han Sans ne contient pas** les caractères `·`, `à`, `ô` ni `—` — ils sont absents
  de la police d'origine, pas du sous-ensemble. Ils tombaient déjà dans la police de repli
  avant cette modification : **aucune régression.**
- Instrument Serif **droit** et Noto Sans KR **400** sont déclarés mais jamais employés par
  la maquette (tout le serif est en italique, tout le hangul est en 700). Les navigateurs ne
  chargent une police que si elle sert : ces fichiers ne coûtent rien et couvrent un usage
  futur.

**Test de non-régression :** ouvrir l'onglet Réseau, filtrer sur « third-party ». Le compte
doit rester à zéro.

---

## 5. Domaine, `sitemap.xml`, `robots.txt` — rien à reprendre

**Le site ne contient aucun nom de domaine** : pas de `sitemap.xml`, pas de `robots.txt`,
aucune balise `canonical`, aucun `og:url`. Le domaine définitif n'a donc pas pu être relevé,
et **il n'a pas été inventé**.

Conséquences, à traiter une fois le domaine arrêté :

- [ ] créer `sitemap.xml` avec les quatre entrées (`index.html`, `mentions-legales.html` et
      `confidentialite.html` en `priority` 0.2, `lastmod` 2026-07-17) ;
- [ ] créer `robots.txt` pointant le sitemap ;
- [ ] ajouter `<link rel="canonical">` et `og:url` sur les trois pages — les autres balises
      Open Graph (`og:type`, `og:title`, `og:locale`) sont déjà en place sur les pages légales.

---

## 6. Autres points relevés

- **« 4,7 ★ — plus de 900 avis Google »** est affiché quatre fois (hero, stats, avis,
  citation). C'est un chiffre **mouvant** : une allégation chiffrée fausse relève des
  pratiques commerciales trompeuses (art. L121-2 du code de la consommation). À réactualiser
  périodiquement, ou à remplacer par une formulation non chiffrée.
- La **citation d'avis client** (« Le meilleur coréen de Nantes… ») n'est pas attribuée à une
  source identifiable. Si elle provient d'un avis Google réel, garder la trace de l'original ;
  sinon, ne pas la présenter comme un avis.
- **Licence de débit de boissons** : la carte vend bière, soju et makgeoli. La licence
  correspondante et l'affichage « interdiction de vente d'alcool aux mineurs » sont des
  obligations **de l'établissement**, à vérifier sur place — le site, lui, porte désormais la
  mention de l'article L3342-1.
- Aucun lien légal ne pointe vers un ancien site : **il n'y avait aucune page légale
  auparavant**, ni mentions légales ni politique de confidentialité. C'est un manquement à
  l'article 6 LCEN qui existe aujourd'hui et que ces deux pages comblent.

---

## 7. À vérifier après la mise en ligne

- [ ] `grep -rn "à fournir\|à confirmer" *.html` ne renvoie plus rien
- [ ] `grep -rn 'googleapis\|gstatic' . --include='*.html' --include='*.css'` ne renvoie rien
- [ ] Aucune requête tierce dans l'onglet Réseau
- [ ] `document.cookie` est vide
- [ ] `robots.txt` et `sitemap.xml` existent et pointent le vrai domaine (§ 5)
- [ ] Le site est déclaré dans Google Search Console
- [ ] La fiche Google Business est cohérente avec les horaires du site
- [ ] Le lien « Création Vokum » du pied de page répond
