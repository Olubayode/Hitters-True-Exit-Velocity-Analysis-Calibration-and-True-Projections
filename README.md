# Hitters-True-Exit-Velocity-Analysis-Calibration-and-True-Projections

## Baseball Performance Metrics Analysis Project
### Overview
This project evaluates hitter performance by analyzing batted ball metrics from two measurement systems (System A and System B). The primary objective is to project the "true" average speed-off-bat for each batter in the following season while addressing inconsistencies and missing data between the two systems.

### Key Highlights
Calibration: System B was calibrated to align with the more accurate System A, ensuring consistent and reliable projections.

Data Cleaning: Missing data and outliers were strategically treated to maintain the dataset's structure and variability.

Projections: Batter-specific and hit-type-specific speed-off-bat projections were generated to capture individual performance trends.

### Data Overview
The dataset contains measurements for individual batted balls:

Speed-off-bat: Exit velocity (mph) measured by Systems A and B.

Launch angle: Initial vertical angle (degrees) measured by Systems A and B.

Hit type: Categorical variable indicating the type of hit (fly_ball, ground_ball, line_drive, popup).

Player IDs: Unique identifiers for batters and pitchers.

### Key Observations
System A: Records higher speeds with greater consistency.

System B: Tends to underestimate speeds and shows greater variability.

Missing data and outliers were significant challenges:

10.32% missing data in System A’s speed measurements.

1.91% missing data in System B’s speed measurements.

###  Approach
1. Data Cleaning

Outlier Detection and Removal: Outliers in speed and angle measurements were identified using box plots and removed to reduce noise.

Missing Data Treatment:

Median imputation was performed for speed and angle values, grouped by hit type and batter.

A fallback strategy used broader hit type medians when batter-specific data was insufficient.

2. Calibration of System B

Linear Regression Models:

Separate models were developed for each hit type (fly_ball, ground_ball, line_drive, popup).

Exit velocity and launch angle were adjusted based on System A’s benchmarks.

### Key Calibration Insights:
Ground balls required significant baseline speed adjustments.

Line drives and fly balls required minor adjustments for both speed and angle.

3. Weighted Calibration

A weighted average of System A and calibrated System B values was computed to form a unified metric. Weights were inversely proportional to the RMSE of each system, ensuring optimal reliability.

4. Projection of True Speed

Grouping: Data was grouped by batter and hit type to calculate average exit velocities for each combination.

Stability: Grouping smoothed out random noise and provided reliable "true" speed benchmarks.

5. Performance Categorization

Batters were classified based on their projected performance relative to historical averages:

Above Performance: Significant improvement over historical data.

Maintain Performance: Consistent with historical performance.

Underperform: Slight declines from historical data.

### Results
Calibration Accuracy

Significant reduction in RMSE and MAE after calibration.

Median exit velocity for calibrated System B closely aligned with System A.

True Speed Projections

Low error metrics (MAE: 1.91, RMSE: 3.37) indicated effective alignment with System A’s values.

Individual batter trends revealed key performance insights.

### Performance Categorization
Example results:

Fly Ball: Batter 737 improved from 104.53 to 106.45 mph (Above Performance).

Ground Ball: Batter 438 improved from 96.70 to 97.89 mph (Above Performance).

### Evaluation
This project demonstrates:

Data Management: Effective handling of imperfect data through calibration and imputation.

Projections: Accurate modeling of true speed-off-bat values tailored to individual batters and hit types.

Insights: Clear identification of batter-specific trends for actionable insights.
