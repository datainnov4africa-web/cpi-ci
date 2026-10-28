# Method — experimental consumer price index

AfDB – Data Innovation for Africa (DI4A)

1. **Collection.** Prices already published online — shops, regulators, utilities, telecom operators, open market-price data — are read by an identified robot that reads `robots.txt` first, waits at least the site's `Crawl-delay`, and records a refusal instead of circumventing it.
2. **Item prices.** The price of an item over a period is the geometric mean of its quotes. Outliers (more than 5 robust deviations from the item's median) are flagged and left out of the relatives, never deleted.
3. **Classification.** Every item receives a COICOP 2018 code (rules, optionally a language model when it is confident). Accuracy is measured on annotated samples.
4. **Elementary indices.** Matched items, **Jevons** (geometric mean of price relatives), chained, by COICOP class; each outlet is a stratum with equal weight.
5. **Missing prices** are imputed explicitly from their stratum, for two consecutive periods at most (eleven for seasonal items); a returning item is compared with its imputed price. Prices are never carried forward, except administered tariffs, which stay in force until the next decision.
6. **Replacements** are linked when a product succeeds another in the same outlet, class and label; the price is adjusted for quantity (smaller pack, same price = a rise).
7. **Aggregation** with the official weights by division (or group), **Young/Lowe** form written as a chain with price-updated weights; contributions add up exactly to the change of the all-items index. Divisions without any price read are imputed from the measured ones and flagged.
8. **Robustness**: variants changing one choice at a time, GEKS against chain drift, and a 90 % bootstrap interval over the sample of items.

Reference: IMF, ILO, Eurostat, UNECE, OECD, World Bank (2020), *Consumer Price Index Manual: Concepts and Methods*.

**Experimental statistics**: online buyers are urban and connected; a displayed price is not a transaction; coverage depends on what is published. This index complements the official CPI; it does not replace it.
