# 🏏 Clutchly: The AI-Driven Cricket "Clutch" Engine

**Clutchly** is a high-performance sports analytics project that quantifies the "unquantifiable"—the ability of a player to perform under extreme pressure. While traditional statistics like averages and strike rates provide a snapshot of performance, **Clutchly** treats a cricket match as a **time-varying signal** and uses non-linear machine learning to extract a player's true "Clutch Factor."

---

## 🚀 Overview
The project processes 1,200+ IPL matches to predict win probabilities ball-by-ball. It utilizes an **XGBoost Classifier** to reach a prediction accuracy of **82.06%**, outperforming standard baseline models by incorporating engineered features like "Pressure Delta" and "Momentum."



## 🧠 Technical Architecture

### 1. The Machine Learning Engine (XGBoost v3.0)
The core of the project is a Gradient Boosted Decision Tree model trained on ball-by-ball situational data.
*   **Key Features:** Required Run Rate (RRR), Wickets Lost, Balls Left, Target Difference, and Strike Bowler Availability.
*   **Momentum Signal:** A custom feature, `pressure_delta`, which calculates the change in pressure by comparing the RRR against the actual run rate over the last 3 overs.

### 2. The Mathematical Framework
To identify the most impactful players, the system calculates derivative metrics:

*   **Win Probability Added (WPA):** The change in win probability ($WP$) caused by a single delivery.
    $$WPA = WP_{n} - WP_{n-1}$$
*   **Leverage Index (LI):** A measure of how "critical" a moment is based on the potential volatility of the win probability.
*   **Clutch Impact Score:** The final normalized metric used to rank players.
    $$Clutch\ Impact = \sum (WPA \times LI)$$

---

## 📊 Analytics & Storytelling
The project is visualized through a premium **Power BI Dashboard** designed with a focus on professional visual hierarchy and actionable insights.

*   **The Momentum Worm:** A line chart depicting the "heartbeat" of a chase.
*   **The Finisher Quadrant:** A scatter plot using **Median-based thresholds** to segment players into "Clutch Kings" and "Accumulators."
*   **AI Explainability:** Utilizing **Key Influencer** visuals to show which situational factors (e.g., wickets vs. RRR) are currently driving the win probability.



## 🛠️ Tech Stack
*   **Languages:** Python (Pandas, NumPy, Scikit-Learn)
*   **Modeling:** XGBoost (Extreme Gradient Boosting)
*   **Visualization:** Power BI
*   **Data Source:** Cricsheet (1,200+ IPL JSON/CSV files)

---

## 🏗️ Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Clutchly.git](https://github.com/YOUR_USERNAME/Clutchly.git)
   cd Clutchly
