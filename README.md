# Chicago Blackhawks 5v5 Shot Quality & Slot Generation Analysis
**Author:** Ayden Thongphadith  
**Focus:** NHL Edge Tracking Data | Offensive Geometry | Player Lineup Impact  

---

## 1. Project Overview & Objective
An automated quantitative evaluation assessing the impact of Connor Bedard's lineup presence on the Chicago Blackhawks' 5-on-5 offensive shot distribution and danger profile. 

This analysis compares:
* **Baseline Cohort (Games 1–5):** Regular season games without Connor Bedard (1–4 record).
* **Return Cohort (Games 6–8):** Regular season games with Connor Bedard (vs. Pittsburgh, Winnipeg, and Dallas).

---

## 2. Methodology & Geometric Definitions
* **State Filter:** Filtered exclusively to 5-on-5 unblocked shot attempts (`situationCode == "1551"`: Fenwick events including shots on goal, missed shots, and goals). Special teams and empty-net situations were removed to isolate baseline offensive structure.
* **Coordinate Standardization:** Rotated all event $(x, y)$ coordinates to standardize attacking direction along the positive X-axis ($0 \le x \le 100$).
* **Home-Plate Slot Funnel:** Defined high-danger slot geometry as:
  * Low Slot / Crease: $69 \le x \le 89$, $-9 \le y \le 9$
  * High Slot / Faceoff Dots: $54 \le x < 69$, $-22 \le y \le 22$

---

## 3. Visual Output
![Blackhawks Shot Quality Visual](bedard_slot_impact.png)

---

## 4. Key Findings & Tactical Takeaways
* **Slot Funnel Share:** [Insert final % without Bedard] vs. [Insert final % with Bedard]
* **Defensive Gravity:** Bedard's presence shifts opposing coverage deeper into the home-plate interior, opening weak-side point lanes and high-slot rebound secondary attempts.
* **Coaching Application:** Demonstrates whether offensive zone time is translating into low-danger perimeter volume or direct slot penetration against structured defensive systems.
