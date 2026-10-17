# Chicago Blackhawks 5v5 Shot Quality & Efficiency: Home vs. Away Split "Are they actually playing better at home?"
**Author:** Ayden Thongphadith  
**Focus:** NHL Play-by-Play Tracking | Venue & Matchup Dynamics | Goaltender Quality Impact  

---

## 1. Project Overview & Objective
An empirical spatial and statistical analysis investigating why the Chicago Blackhawks hold a **3–1–0 record at the United Center** compared to a **0–4–0 record on the road** through the opening 8 games of the 2026–27 regular season[cite: 9]. 

While raw attempt metrics suggest Chicago generates higher slot volume on the road[cite: 9], deeper spatial parsing reveals a distinct divergence in net-front finishing, score effects, and opposing goaltender quality[cite: 9].

---

## 2. Methodology & Geometric Pipeline
* **Even-Strength Isolation:** Filtered play-by-play events strictly to 5-on-5 unblocked shot attempts (`situationCode == "1551"`: shots on goal, missed shots, and goals). Special teams, 4-on-4 play, and empty-net scenarios are excluded.
* **Coordinate Standardization:** Mapped all coordinates to an offensive half-rink frame ($0 \le x \le 100$, $-42.5 \le y \le 42.5$) using coordinate reflection for shots in the negative half.
* **Home-Plate Slot Definition:**
  * **Low Slot / Crease Mouth:** $69 \le x \le 89$, $-9 \le y \le 9$
  * **High Slot / Funnel:** $54 \le x < 69$, $-22 \le y \le 22$
* **Rate Metric Benchmark:** Pace metrics are normalized to attempts per 60 minutes using the standard industry baseline of 48.0 minutes of 5v5 ice time per regulation game.

---

## 3. Data Visualization
![Blackhawks Home vs Away Shot Quality](bedard_slot_impact.png)

---

## 4. Key Metrics Summary

| Metric | Home (United Center) | Away (Road Venues) | Divergence / Context |
| :--- | :---: | :---: | :--- |
| **Record** | **3–1–0**[cite: 9] | **0–4–0**[cite: 9] | +3 Net Wins at Home |
| **Games Played** | 4 GP[cite: 9] | 4 GP[cite: 9] | Even sample size |
| **5v5 Goals Scored** | **8**[cite: 9] | **5**[cite: 9] | +60% goal output at home |
| **Total 5v5 Attempts** | 105[cite: 9] | 115[cite: 9] | Road volume driven by trailing state |
| **5v5 Shooting % (Sh%)** | **7.6%**[cite: 9] | **4.3%**[cite: 9] | **+3.3% conversion rate at home** |
| **Slot Share %** | 39.0%[cite: 9] | 43.5%[cite: 9] | Road attempts forced from high slot |
| **Pace (Attempts / 60)** | 32.8[cite: 9] | 35.9[cite: 9] | Trailing urgency on the road |

---

## 5. Tactical & Analytical Insights

### A. The Finishing Paradox: Crease-Clustering vs. High Slot Volume
On the road, Chicago recorded a higher slot share (43.5% vs. 39.0%) and greater pace (35.9 vs. 32.8 Att/60)[cite: 9]. However, spatial distribution illustrates that road slot chances were pushed outward toward the hashmarks and faceoff dots[cite: 9]. At home, Chicago's slot generation is clustered directly on top of the blue paint, producing second-chance rebounds, screens, and tap-ins that converted at **7.6%** compared to just **4.3%** away[cite: 9].

### B. Score Effects & Trailing Game States
Chicago trailed early in road matchups (e.g., at Vegas, Utah, and against the Islanders). When trailing, teams experience systemic "score effects"—abandoning conservative defensive structures to force direct, unblocked attempts from anywhere inside the zone. While this inflates unblocked shot volume, these rush attempts lack pre-shot puck movement and screen support.

### C. Opposing Goaltending Quality (PDO & Matchup Split)
A decisive factor in the 7.6% vs. 4.3% finishing disparity is the calibre of goaltending faced across the venues[cite: 9]:
* **Home Wins (3–1–0):** Chicago faced younger, backup, or tandem goaltenders in their victories—specifically Sergei Murashov (rookie debut), Stuart Skinner, and Joel Hofer—allowing net-front rebounds and deflections to turn into goals[cite: 9]. Their lone home loss came against Carolina's Pyotr Kochetkov.
* **Road Losses (0–4–0):** Chicago ran into high-end established starters—Ilya Sorokin (NYI), Ukko-Pekka Luukkonen (BUF), Karel Vejmelka (UTA), and Carter Hart (VGK). High-leverage saves against structured rush chances suppressed Chicago's road conversion to 4.3% despite high volume[cite: 9].

---

## 6. How to Run
```bash
# Clone the repository
git clone [https://github.com/ayden-thongphadith/blackhawks-slot-analytics.git](https://github.com/ayden-thongphadith/blackhawks-slot-analytics.git)
cd blackhawks-slot-analytics

# Install dependencies
pip install matplotlib numpy pandas requests

# Run analysis and render plot
python script1.py
