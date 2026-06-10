# aprèsimpôt.fr — déploiement et mise en route

Site statique complet : simulateur PEA / Assurance-vie / CTO / PER + 5 guides SEO + sitemap, robots, 404, mentions légales. Zéro dépendance, zéro backend.

## Structure

```
site/
├── index.html                  # Simulateur (page d'accueil)
├── style.css                   # CSS des guides
├── mentions-legales.html       # TEMPLATE — champs [XXX] à compléter
├── 404.html
├── robots.txt
├── sitemap.xml                 # Domaine à remplacer si différent
└── guides/
    ├── index.html
    ├── pea-ou-cto-etf.html
    ├── fiscalite-rachat-assurance-vie-8-ans.html
    ├── abattement-4600-assurance-vie.html
    ├── retrait-pea-avant-5-ans.html
    └── per-ou-pea-tmi-30.html
```

## Mise en ligne (ordre recommandé)

1. **Domaine** (~10 €/an) : apresimpot.fr ou équivalent, chez OVH / Gandi / Cloudflare.
   Si le domaine final diffère, faire un rechercher-remplacer global de
   `https://www.apresimpot.fr` dans tous les fichiers (balises canonical + sitemap + robots).

2. **Déploiement** : repo GitHub → Settings → Pages → branche main, racine = ce dossier.
   Ajouter le domaine custom dans Pages + créer les enregistrements DNS (A/CNAME) chez le registrar.
   (Vercel fonctionne aussi : import du repo, zéro config.)

3. **Micro-entreprise** : déclaration sur formalites.entreprises.gouv.fr (activité : services,
   code APE type 6312Z ou 7022Z). Nécessaire pour percevoir les commissions.
   Vérifier la compatibilité avec la convention de stage en cours.

4. **Mentions légales** : compléter les champs [PRÉNOM NOM], [SIREN], [ADRESSE], [EMAIL]
   dans mentions-legales.html, et supprimer la mention d'hébergeur non retenue.

5. **Programmes d'affiliation** : candidater une fois le site en ligne (les plateformes vérifient).
   - Plateformes : Affilae, Effiliation, Awin, Kwanko — chercher Linxea, Lucya Cardif,
     Goodvest, Yomoni, Trade Republic, Bourse Direct, Saxo.
   - BoursoBank fonctionne par parrainage (pas d'affiliation classique).
   - Une fois acceptés : remplacer les 4 liens `href="#"` marqués `data-affiliate`
     dans index.html (pea, av, cto, per) par les URL trackées. Conserver `rel="sponsored nofollow"`.

6. **Google Search Console** : ajouter la propriété, vérifier via DNS,
   soumettre https://www.apresimpot.fr/sitemap.xml. Bing Webmaster Tools en bonus (2 min).

7. **Mesure d'audience** (optionnel mais recommandé) : Plausible ou GoatCounter
   (sans cookie → pas de bannière de consentement). Mettre à jour la section
   « Données personnelles » des mentions légales si ajouté.

## Rythme de croisière

- Publier 3-4 nouveaux guides/mois (demander les batchs suivants à Claude ; cibles prioritaires :
  « assurance vie ou PER succession », « PEA 150 000 euros atteint », « fiscalité dividendes CTO »,
  « PFU ou barème progressif », « transfert assurance vie loi Pacte »).
- Mettre à jour sitemap.xml à chaque publication (ajouter une ligne <url>).
- Réviser les barèmes chaque janvier (loi de finances) : abattements, PFU, plafonds.

## Avertissement conformité

Le site ne fournit que de l'information générique : ne jamais ajouter de fonctionnalité de
recommandation personnalisée (questionnaire de profil → produit précis) sans statut CIF.
Les disclaimers présents dans les footers et les mentions légales doivent rester en place.
