# Méthode — indice expérimental des prix à la consommation

AfDB – Data Innovation for Africa (DI4A)

1. **Collecte.** Des prix déjà publiés en ligne — boutiques, régulateurs, services publics, opérateurs télécoms, données ouvertes de prix de marché — sont lus par un robot identifié qui lit d'abord le `robots.txt`, attend au moins le `Crawl-delay` du site et consigne un refus au lieu de le contourner.
2. **Prix des articles.** Le prix d'un article sur une période est la moyenne géométrique de ses relevés. Les valeurs aberrantes (plus de 5 écarts robustes de la médiane de l'article) sont signalées et écartées des rapports, jamais supprimées.
3. **Classification.** Chaque article reçoit un code COICOP 2018 (règles, et en option un modèle de langage quand il est sûr). La justesse est mesurée sur des échantillons annotés.
4. **Indices élémentaires.** Articles appariés, **Jevons** (moyenne géométrique des rapports de prix), chaîné, par classe COICOP ; chaque point de vente est une strate de poids égal.
5. **Les prix manquants** sont imputés explicitement par leur strate, deux périodes consécutives au plus (onze pour les produits saisonniers) ; un article qui revient est comparé à son prix imputé. Les prix ne sont jamais reconduits, sauf les tarifs administrés, en vigueur jusqu'à la décision suivante.
6. **Les remplacements** sont raccordés quand un produit succède à un autre dans le même point de vente, la même classe et le même libellé ; le prix est ajusté de la quantité (paquet plus petit au même prix = hausse).
7. **Agrégation** avec les poids officiels par division (ou groupe), forme **Young/Lowe** écrite en chaîne avec poids actualisés par les prix ; les contributions s'additionnent exactement à la variation de l'ensemble. Les divisions sans aucun prix lu sont imputées par les divisions mesurées, et signalées.
8. **Robustesse** : variantes changeant un seul choix à la fois, GEKS contre la dérive de chaînage, intervalle bootstrap à 90 % sur l'échantillon des articles.

Référence : FMI, OIT, Eurostat, CEE-ONU, OCDE, Banque mondiale (2020), *Consumer Price Index Manual: Concepts and Methods*.

**Statistique expérimentale** : les acheteurs en ligne sont urbains et connectés ; un prix affiché n'est pas une transaction ; la couverture dépend de ce qui est publié. Cet indice complète l'IPC officiel ; il ne le remplace pas.
