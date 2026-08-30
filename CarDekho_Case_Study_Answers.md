# Case Study: CarDekho Data Analysis — Answers

**Dataset:** 301 vehicle listings, 9 columns (`Car_Name, Year, Selling_Price, Present_Price, Kms_Driven, Fuel_Type, Seller_Type, Transmission, Owner`). Prices are in ₹ lakhs. The dataset mixes **200 cars** and **101 two-wheelers** — two-wheelers were identified by brand prefixes in the name (Honda, Hero, Bajaj, TVS, Yamaha, Royal Enfield, KTM, Suzuki, Hyosung, Mahindra Mojo, UM).

## General questions (1–16)

1. **Manufacturing year range:** vehicles span **2003 to 2018**.
2. **Lowest selling price:** **₹0.1 lakh** (₹10,000).
3. **Highest selling price:** **₹35.0 lakh**.
4. **Total records:** **301**.
5. **Missing records:** **None** — all 9 columns are fully populated across all 301 rows.
6. **Distinct vehicles (by name):** **98** unique models.
7. **Most sold vehicle:** the **City** (Honda City), appearing **26 times** — the single most listed model.
8. **CNG vehicles:** **2** — a 2015 Wagon R and a 2011 SX4. CNG is rare in this data (0.7% of listings).
9. **Individually sold vehicles:** **106** listed directly by an individual owner (vs. 195 through dealers).
10. **Automatic transmission vehicles:** **40** (the remaining 261 are manual).
11. **Single-owner vehicles:** **290** vehicles show `Owner = 0` (no prior owner before the seller) — the large majority of the dataset.
12. **Most/least cost-depreciated vehicle** (Present Price − Selling Price):
    - Most depreciated: **Toyota Land Cruiser**, down **₹57.6 lakh** from its present-day price.
    - Least depreciated: **Honda Activa 4G**, down only **₹0.03 lakh** — it barely lost value.
13. **Brands least/most affected by depreciation** (average % depreciation, grouped by the first word of the model name — note the data has no separate "make" column for cars, so this groups by name prefix, which is the true brand for two-wheelers):
    - Least depreciation: **Maruti Vitara Brezza** (~6%), **UM** Renegade (~7%), **Hyundai Creta** (~13%).
    - Most depreciation: **Land Cruiser** (~62%), **Maruti 800** (~85%), **Toyota Camry** (~89%). Premium/older models depreciate hardest in percentage terms.
14. **Factors affecting depreciation:** correlating each factor with % depreciation —
    - **Age: r ≈ 0.85** (strong positive) — the single biggest driver of depreciation.
    - **Kms driven: r ≈ 0.51** (moderate positive) — more mileage, more value lost.
    - **Owner count: r ≈ 0.22** (weak positive) — a modest effect.
    - Age dominates; mileage matters but less than age alone.
15. **Does selling price depend on age and kms driven?** Yes, but the relationship is modest, not strongly linear:
    - Selling price vs. age: **r ≈ −0.24** (older vehicles sell for somewhat less).
    - Selling price vs. kms driven: **r ≈ +0.03** (essentially no direct relationship on its own — mileage matters more in combination with age than alone, since kms driven and age are themselves correlated at r ≈ 0.52).
16. **Vehicles newer than 2014 (i.e., 2015–2018):** **147** — just under half the dataset (49%).

## Two-wheelers only (17–21)

- **Two-wheeler count:** 101.
17. **Oldest bike sold:** **Hero Super Splendor**, from **2005**.
18. **Newest bike sold:** **UM Renegade Mojave**, from **2017**.
19. **Most sold bike:** the **Royal Enfield Classic 350**, sold **7 times**.
20–21. **Best two-wheeler "deal":** Comparing each bike's actual selling price to the price predicted from its age and mileage (a simple regression baseline), the **2016 Royal Enfield Thunder 500** stands out — it sold for **₹1.75 lakh**, well above its expected price of **~₹0.80 lakh** for its age/mileage. Royal Enfields as a group command a premium over other bikes of similar age, likely reflecting strong resale demand and brand loyalty for the marque.

## Cars only (22–25)

22. **Car count:** **200**.
23. **Oldest car sold:** the **Maruti 800**, from **2003**.
24. **Newest car sold:** the **Vitara Brezza**, from **2018**.
25. **Best car "deal":** Using the same expected-price baseline, the **2010 Toyota Land Cruiser** is the standout — it sold for **₹35 lakh** against a baseline expectation of only **~₹5.1 lakh** for a vehicle of its age/mileage. This reflects that Land Cruiser is a luxury SUV whose absolute price sits far outside the range the rest of the dataset was used to calibrate, rather than a "steal" in the everyday sense — it's an outlier worth flagging and treating separately in any pricing model, not proof of an unusually good bargain.

---
*Methodology note: "expected price" in Q20/21 and Q25 comes from a simple least-squares regression of selling price on vehicle age and kilometers driven, fit separately for two-wheelers and cars. It's a rough baseline, not a full valuation model — but it's a reasonable way to flag listings that sold notably above (or below) what similar vehicles fetched.*
