# 6/24 Raw Notes - Flamethrower Project

## Goal

The goal is to make a flamethrower out of some "cleaning solution".

I should be able to add other stuff like WD-40 maybe cuz WHY NOT 

Stuff flammable that is cool:
- **Hand sanitizer** → when I did it, cool flameballs
- **WD-40** → seems like it's good
- **AXE** → wanna see how it does tho

For that, I wanna understand how the fire would work.

## Initial Chemistry Approach

Since `CH₄ (g) + 2 O₂ (g) → CO₂ (g) + 2 H₂O (g)`, the idea is to see what has more CH₄ per dollar and per gram.

After further research, this isn't entirely good for my purpose since methane is not present in other chems. Instead I will use approximations of Energy (MJ/kg).

**Questions to answer:**
- How much chemical energy is in each fuel source?
- How much you pay per unit of that energy ($/MJ)?

The idea is to see if this project is practical.

## General Hydrocarbon Combustion

```
CₓHᵧ + (x + y/4) O₂ → x CO₂ + (y/2) H₂O
```

## Fuel Energy Content Research

### 1. Methane (CH₄) → ~55.5 MJ/kg

**Calculation:**
Methane's combustion reaction:
```
CH₄ + 2 O₂ → CO₂ + 2 H₂O + Energy
```

The enthalpy of combustion (ΔH°c) for methane is −890 kJ/mol.

Molar mass of CH₄ = 16 g/mol

Energy per kg = (890 kJ/mol) / (0.016 kg/mol) = 55,625 kJ/kg ≈ 55.6 MJ/kg

**Result:** **~55.6 MJ/kg**

---

### 2. Kerosene

> **Source:** [Wikipedia - Kerosene](https://en.wikipedia.org/wiki/Kerosene)

The footnote source is paid for access but "The heat of combustion of kerosene is similar to that of diesel fuel; its lower heating value is 43.1 MJ/kg (around 18,500 Btu/lb), and its higher heating value is 46.2 MJ/kg (19,900 Btu/lb).[15]"

Since the lower heating value (LHV) of 43.1 MJ/kg represents the net energy released when the water produced during combustion remains as vapor, I will consider the MJ/kg as 43.1.

**Result:** **43.1 MJ/kg**

---

### 3. Diesel

> **Source:** [IRU - Diesel Litre Equivalent](https://www.iru.org/system/files/Diesel%20Litre%20Equivalent%20(DLE).pdf)

According to this, the MJ/kg of diesel is 43 MJ/kg.

**Result:** **43.0 MJ/kg**

---

### 4. Ethanol

> **Source:** [Engineering Toolbox - Heat of Combustion](https://www.engineeringtoolbox.com/standard-heat-of-combustion-energy-content-d_1987.html)

For ethanol: "The heat of combustion of ethanol, ΔHc °(C₂H₆O, l) = 1366.91(kJ/mol) × 1000(g/kg) / 48.08 (g/mol) = 29664 kJ/kg ethanol = 29.7 MJ/kg = 12754 BTU/lb = 7086 kcal/kg"

**Result:** **29.7 MJ/kg**

---

### 5. WD-40

> **Source:** [WD-40 Myths & Legends](https://www.wd40.com/myths-legends-fun-facts/)

This remains very tricky; no tests were done and the chemical composition is not available anywhere. I searched for hours and this took a majority of my research time. However, as per the source, "WD-40 Multi-Use Product contains petroleum distillates".

For that reason, I'll associate it with kerosene: **~43.1 MJ/kg**

**Result:** **~43.1 MJ/kg**

---

### 6. AXE Body Spray

> **Source:** [AXE Proximity Deodorant Bodyspray MSDS](https://www.whatsinproducts.com/files/brands_pdf/9618_21010028%20MSDS%20Axe%20Proximity%20Deodorant%20Bodyspray,%20Bergamot.pdf)

This has a list of ingredients, which allows me to calculate that since:
- **Alcohol Denat. (SD Alcohol 40-B):** 40–65%
- **Isobutane:** 30–40%
- **Butane:** 30–40%
- **Hydrofluorocarbon 152a:** 20–40%
- **Propane:** 5–10%

Averages of this would be:
- **Propane:** 7.5%
- **Hydrofluorocarbon 152a:** 30%
- **Butane:** 35%
- **Isobutane:** 35%
- **Alcohol Denat. (SD Alcohol 40-B):** 52.5%

Which in total is **160%**, not 100%. Need to normalize final value by dividing total energy by 1.6.

---

### AXE Component Energy Content Reference

| Compound | Typical Energy Content (MJ/kg) | Source(s) | Derivation |
|----------|-------------------------------|-----------|------------|
| Propane | 46.4 | NIST Chemistry WebBook, Wikipedia | [NIST WebBook](https://webbook.nist.gov/cgi/cbook.cgi?ID=C74986&Mask=FFF): ΔcH°gas = -2219.2 ± 0.46 kJ/mol (Pittam and Pilcher, 1972). Molar mass = 44.0956 g/mol. Calculation: 2219.2 kJ/mol ÷ 44.0956 g/mol × 1000 g/kg = 50,364 kJ/kg = 50.4 MJ/kg. Using net value: **46.4 MJ/kg** |
| Butane (n-Butane, C₄H₁₀) | 45.7 | NIST Chemistry WebBook, Wikipedia | [NIST WebBook](https://webbook.nist.gov/cgi/cbook.cgi?ID=C74986&Mask=FFF): ΔcH°gas = -2877.5 kJ/mol. Molar mass = 58.12 g/mol. Calculation: 2877.5 kJ/mol ÷ 58.12 g/mol × 1000 g/kg = 49,519 kJ/kg = 49.5 MJ/kg. Net heating value: **45.7 MJ/kg** (lower heating value, as used in fuel tables) |
| Isobutane (2-methylpropane, C₄H₁₀) | 45.6 | NIST Chemistry WebBook, Wikipedia | [NIST WebBook](https://webbook.nist.gov/cgi/cbook.cgi?ID=C74986&Mask=FFF): ΔcH°gas = -2877.3 kJ/mol. Molar mass = 58.12 g/mol. Calculation: 2877.3 kJ/mol ÷ 58.12 g/mol × 1000 g/kg = 49,515 kJ/kg = 49.5 MJ/kg. Net heating value: **45.6 MJ/kg** (lower heating value, as used in fuel tables) |
| Hydrofluorocarbon 152a (1,1-Difluoroethane, C₂H₄F₂) | 16.5 | NIST Chemistry WebBook, Standard chemical data | [NIST WebBook](https://webbook.nist.gov/cgi/cbook.cgi?ID=C74986&Mask=FFF): ΔcH°gas = -1230.7 kJ/mol. Molar mass = 66.05 g/mol. Calculation: 1230.7 kJ/mol ÷ 66.05 g/mol × 1000 g/kg = 18,634 kJ/kg = 18.6 MJ/kg. Typical rounded value: **16.5 MJ/kg** (depending on reference and net/gross value) |
| Alcohol Denat. (Ethanol, C₂H₅OH) | 30 | NIST Chemistry WebBook, Wikipedia | [NIST WebBook](https://webbook.nist.gov/cgi/cbook.cgi?ID=C74986&Mask=FFF): ΔcH°gas = -1366.8 kJ/mol. Molar mass = 46.07 g/mol. Calculation: 1366.8 kJ/mol ÷ 46.07 g/mol × 1000 g/kg = 29,667 kJ/kg = 29.7 MJ/kg. Typical rounded value: **29.7 MJ/kg** |

---

### AXE Body Spray Energy Calculations

#### Given Composition:
- **Propane:** 7.5% (~46.4 MJ/kg)
- **Hydrofluorocarbon 152a:** 30% (~16.5 MJ/kg)
- **Butane:** 35% (~45.7 MJ/kg)
- **Isobutane:** 35% (~45.6 MJ/kg)
- **Alcohol Denat. (SD Alcohol 40-B):** 52.5% (~30 MJ/kg)
- **Total percentages:** 160%

#### Step-by-Step Calculation

**1. Multiply each component's percentage (as a decimal) by its energy content:**

**Propane (7.5%):**
```
0.075 × 46.4 = 3.48 MJ/kg
```

**HFC-152a (30%):**
```
0.30 × 16.5 = 4.95 MJ/kg
```

**Butane (35%):**
```
0.35 × 45.7 = 15.995 MJ/kg
```

**Isobutane (35%):**
```
0.35 × 45.6 = 15.96 MJ/kg
```

**Alcohol Denat. (52.5%):**
```
0.525 × 30 = 15.75 MJ/kg
```

**2. Add all the results:**
```
3.48 + 4.95 + 15.995 + 15.96 + 15.75 = 56.135 MJ/kg
```

**3. Divide by the total percentage (as a decimal):**
```
56.135 / 1.6 = 35.08 MJ/kg
```

**Final Weighted Average Energy Content:** **≈ 35.1 MJ/kg**

---

## Summary

| Fuel | Energy Content (MJ/kg) | Notes |
|------|----------------------|-------|
| Methane | 55.6 | Highest energy density |
| Kerosene | 43.1 | Standard reference |
| Diesel | 43.0 | Similar to kerosene |
| WD-40 | ~43.1 | Estimated (petroleum distillates) |
| AXE Body Spray | ~35.1 | Calculated from components |
| Ethanol | 29.7 | Lowest of tested fuels |

---

## Next Steps

1. Calculate cost per MJ for each fuel
2. Test actual flammability and burn characteristics
3. Build prototype flamethrower
4. Compare performance and safety

---

## Notes

- Hand sanitizer made cool flameballs when tested
- WD-40 seems promising due to high energy density
- AXE has moderate energy but interesting composition
- All calculations are approximations 