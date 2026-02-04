# Impact-of-Age-21-Legally-assess-to-alcohol-on-fatal-car-accidents.
Causal analysis of the minimum legal drinking age using fuzzy regression discontinuity and NHTSA FARS data to study alcohol use and fatal traffic accidents.
- - - 
## Project Overview
This project studies whether turning 21—the minimum legal drinking age in the United States—causally increases alcohol involvement among drivers involved in traffic crashes. The analysis exploits the sharp policy cutoff at age 21 as a natural experiment and applies both **Sharp** and **Fuzzy Regression Discontinuity Designs (RDD)** to estimate causal effects.

Because compliance with the legal drinking age is imperfect, the study emphasizes a **Fuzzy RDD** framework to estimate the **Local Average Treatment Effect (LATE)** at the cutoff.

---

## Outcome Variable
- **ALC_RES_binary**: Binary indicator equal to 1 if a driver involved in a traffic crash tested positive for alcohol, and 0 otherwise.

---

## Treatment Variable
- **Treatment (Age ≥ 21)**: Indicator variable equal to 1 if the driver is legally eligible to consume alcohol (age 21 or older), and 0 if under 21.

---

## Control Variables
- **Gender** (male / female)
- **Hour of crash**, which may influence alcohol involvement

---

## Research Design

### Regression Discontinuity Design (RDD)
The identification strategy relies on comparing drivers just below and just above the legal drinking age of 21. Individuals near the cutoff are assumed to be similar in observable and unobservable characteristics, except for legal access to alcohol.

Two RDD frameworks are considered:

#### Sharp RDD
- Treatment assignment is perfectly determined by age.
- Drivers aged 21 or older are treated; drivers under 21 are controls.

#### Fuzzy RDD
- Compliance with the legal drinking age is imperfect (e.g., underage drinking or abstention among those over 21).
- The age-21 cutoff is used as an **instrument** for actual alcohol consumption.
- This approach identifies the **Local Average Treatment Effect (LATE)** for drivers whose alcohol consumption changes due to legal eligibility.

---

## Potential Outcomes Framework
Let:
- \( Y_i(1) \) denote alcohol involvement for driver *i* if age ≥ 21
- \( Y_i(0) \) denote alcohol involvement for driver *i* if age < 21

The parameter of interest is:

\[
\text{LATE} = \mathbb{E}[Y_i(1) - Y_i(0) \mid \text{Age} = 21]
\]

---

## Identification Strategy
The causal effect is identified by exploiting the discontinuous change in legal drinking eligibility at age 21. In the Fuzzy RDD framework, age eligibility serves as an instrument for actual alcohol consumption, allowing consistent estimation in the presence of imperfect compliance.

---

## Validity Considerations

### Internal Validity
Potential threats include:
- Missing alcohol test results for some drivers
- Imperfect compliance with the legal drinking age
- Confounding factors correlated with turning 21 (e.g., graduation timing or birthdate clustering)

### External Validity
The data are derived from traffic crash reports and therefore may not generalize to all young drivers, particularly those not involved in accidents.

---

## Data Summary
- **Observations**: 625,520 driver-level records
- **Mean age**: 64.6 (identification focuses on drivers near age 21)
- **Alcohol-positive rate**: ~23–24%
- **Gender**: ~66% male
- **Average crash hour**: 13 (1:00 PM)

Drivers under 21 have an alcohol-positive rate of **11.77%**, compared to **26.25%** for drivers aged 21 or older, indicating a sharp increase at the legal drinking age. Balance checks show modest differences in gender and crash timing across groups.

---

## Key Takeaways
- Alcohol involvement increases sharply at age 21.
- Fuzzy RDD accounts for imperfect compliance with the legal drinking age.
- The framework identifies causal effects locally at the policy cutoff.
- Results emphasize the importance of policy thresholds in causal inference.

---

## Tools & Methods
- Regression Discontinuity Design (Sharp & Fuzzy)
- Instrumental Variables / 2SLS
- Causal inference framework
- Python / R (data cleaning, estimation, visualization)

---

## References
- Cunningham, S. (2021). *Causal Inference: The Mixtape*
- Imbens & Lemieux (2008)
- Lee & Lemieux (2010)
- NHTSA Fatality Analysis Reporting System (FARS)
