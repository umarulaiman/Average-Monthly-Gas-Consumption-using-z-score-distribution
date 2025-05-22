# Average-Monthly-Gas-Consumption-using-z-score-distribution

Gas Consumption Cleaning & Analysis

This Python script loads daily gas‐consumption data, cleans outliers and zero‐usage days, computes monthly and overall averages (both before and after cleaning), and produces informative visualizations. It’s designed to help operations and analytics teams quickly understand consumption trends and identify anomalous days.

🚀 Features
- Data loading from a CSV with date parsing
- Outlier detection via z-scores (±2.5σ)
- Holiday/zero-usage filtering (drops any day with consumption = 0)
- Monthly aggregation: raw vs. cleaned averages
- Overall average: raw vs. cleaned
- Console reports of removed points and summary tables
- Plots:
  1. Monthly cleaned averages with overall average line
  2. Daily original vs. cleaned consumption time series
  3. Z-score histogram overlaid with the standard normal PDF

📋 Requirements
- Python 3.7+
- pandas
- NumPy
- Matplotlib

Install dependencies via:
pip install pandas numpy matplotlib

💾 Data Format
The script expects a CSV file named PlannedvsActual.csv (or update the filename in the code) with at least these two columns:
- date: date in DD/MM/YYYY (or YYYY-MM-DD)
- consumption: numeric daily gas consumption (GJ/day)

⚙️ Usage
1. Place your PlannedvsActual.csv in the same folder as the script.
2. Run the script:
   python clean_analyze_gas.py
3. Console output will display:
   - List of removed dates (zeros + extreme outliers)
   - Monthly averages before and after cleaning
   - Overall average before and after cleaning
4. Interactive plots will open one by one. Close each to proceed.

📈 Output Interpretation
- Removed Data Points: Any day with zero consumption or with a z-score outside ±2.5.
- Monthly Averages (Raw vs. Cleaned): See how outliers/holidays skewed the averages.
- Overall Averages: Quick metric for reporting.
- Plots:
  - Trend Plot: Shows month-end averages against the overall baseline.
  - Time Series: Highlights which daily points were dropped.
  - Z-score Distribution: Verifies assumption of normality and cutoff thresholds.

🧩 Script Breakdown
1. Load & parse data with pandas.
2. Compute mean, standard deviation, and z-scores.
3. Filter out zeros and extreme dips (|z| > 2.5).
4. Aggregate monthly averages on both raw and cleaned sets.
5. Print summaries and removed points to console.
6. Plot results using Matplotlib.

🔧 Customization
- Change cutoff: Adjust the cutoff = 2.5 line to a different σ-threshold.
- Date format: Modify dayfirst=True if your CSV uses YYYY-MM-DD.
- Filename: Update the pd.read_csv('PlannedvsActual.csv', …) path.

📄 License & Attribution
This script was developed to support data-driven operational insights in gas-distribution analytics. Feel free to adapt under the MIT License.

Last updated: May 2025
