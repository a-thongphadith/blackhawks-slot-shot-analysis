# Chicago Blackhawks 5v5 Shot Quality & Efficiency: Home vs. Away Split. Why are they winning at Home instead of Away?
**Author:** Ayden Thongphadith  
**Focus:** NHL Edge Tracking Data | Venue Impact | 5v5 Finishing Dynamics  

---

## 1. Project Overview & Objective
A spatial and quantitative evaluation examining the Chicago Blackhawks' 5-on-5 offensive distribution and conversion across home and road environments through the first 8 games of the 2026–27 season.

* **Home Cohort (United Center | 4 GP):** 3–1–0 record
* **Away Cohort (Road Venues | 4 GP):** 0–4–0 record

---

## 2. Methodology & Geometric Definitions
* **State Filter:** Filtered strictly to 5-on-5 unblocked shot attempts (`situationCode == "1551"`: shots on goal, missed shots, and goals). Special teams and empty-net states excluded.
* **Coordinate Standardization:** Rotated all $(x, y)$ coordinates to standard offensive-zone orientation ($0 \le x \le 100$).
* **Home-Plate Slot Funnel:**
  * Low Slot / Crease: $69 \le x \le 89$, $-9 \le y \le 9$
  * High Slot / Hashmarks: $54 \le x < 69$, $-22 \le y \le 22$

---

## 3. Visual Output
![Blackhawks Shot Quality Visual](bedard_slot_impact.png)

---

## 4. Key Findings & Tactical Insights
* **Finishing Disparity:** Chicago converts at **7.6% (8 goals on 105 attempts)** at home versus **4.3% (5 goals on 115 attempts)** on the road, explaining the split in win-loss records despite trailing-driven shot volume away from home.
* **Crease Clustering:** At the United Center, high-danger generation is tightly packed within the 6-foot crease perimeter, yielding high-percentage deflection and rebound goals. On the road, attempts are diffused into the high slot and dot perimeters against established defenses.
* **Score Effects:** The road sample shows a higher raw attempt pace (35.9 vs. 32.8 Att/60) and higher slot share (43.5% vs. 39.0%), reflecting trailing game states where Chicago pushed direct rush attempts to overcome deficits.
