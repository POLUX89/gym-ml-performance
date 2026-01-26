# Data Dictionary
Rehab Strength Dashboard

This document defines the meaning, granularity, and limitations
of all datasets used in the Rehab Strength Dashboard.

This is the canonical reference for analysis, visualization,
and modeling decisions.

## 1. Strong Workouts Dataset

### Unit of Observation
- One row represents **one exercise set** performed during a workout session.

### Granularity
- Multiple rows per workout session
- Multiple sessions per week

### Key Fields

- date  
  Meaning: Calendar date when the set was performed.  
  Type: Date  
  Risk: Does not capture fatigue or readiness.

- exercise_name  
  Meaning: Name of the exercise performed.  
  Type: Categorical  
  Notes: Same exercise appears many times.

- weight  
  Meaning: External load used.  
  Type: Numeric  
  Risk: Load alone ≠ stress.

- reps  
  Meaning: Number of repetitions.  
  Type: Numeric  

- RPE  
  Meaning: Subjective effort rating.  
  Type: Ordinal  
  Warning: Should not be treated as continuous without care.

### Captures Well
- External training load
- Volume accumulation

### Does NOT Capture
- Pain
- Technique quality
- Psychological stress

## 2. Sleep Dataset

### Unit of Observation
- One row represents **one night of sleep**.

### Granularity
- Daily

### Key Fields

- date  
  Meaning: Night associated with the sleep record.  
  Type: Date  
  Risk: Does not capture fatigue or readiness.

- Score  
  Meaning: Garmin score for sleep 0-100
  Type: Numeric  
  Risk: Affects training on the following day.

- Resting Heart Rate  
  Meaning: RHR associated with the sleep record.  
  Type: Numeric  
  Risk: Affects training on the following day

- Body Battery  
  Meaning: The body battery recoverd from sleep (0-100)
  Type: Numeric  
  Risk: Could affects training on the following day & Mood overall.

- Pulse OX  
  Meaning: Oxigen Saturation in Blood during the sleep  
  Type: String  
  Risk: Could affects training on the following day

- Respiration
  Meaning: Average respiration during sleep
  Type: Numeric 
  Risk: Not known

- HRV Status
  Meaning: Average Heart Rate Variability during sleep
  Type: Numeric 
  Risk: Affects training on the following day

- Quality
  Meaning: Categorical classifier for Sleep Score
  Type: String 
  Risk: Same as Sleep Score

  - Duration
  Meaning: Duration of Sleep in HH:MM
  Type: String 
  Risk: Same as Sleep Score

- Sleep Need
  Meaning: The amount of sleep in HH:MM needed
  Type: String 
  Risk: Could affect training on the followin day

- total_sleep_time
  Meaning: Total duration of sleep.  
  Type: Numeric  

- Bedtime  
  Meaning: Percent of time asleep while in bed.  
  Type: Numeric  
  Warning: Quantity ≠ quality.

- Wake Time  
  Meaning: Percent of time asleep while in bed.  
  Type: Numeric  
  Warning: Quantity ≠ quality.


### Captures Well
- Sleep duration trends
- Large disruptions

### Does NOT Capture
- Sleep stages accuracy
- External stressors

## 3. HRV

### Unit of Observation
- One row represents **one day**.

### Granularity
- Daily

### Key Fields

- date  
  Meaning: Day associated with recovery score.  
  Type: Date  

- Overnight HRV
  Meaning: Sleep HRV Average  
  Type: String

- Baseline
  Meaning: A calculated range of HRV
  Type: String

- 7d avg
  Meaning: Seven day average of HRV
  Type: String

- Strees
  Meaning: Daily average stress
  Type: Numeric

- RHR
  Meaning: Resting Heart Rate during sleep
  Type: Numeric

### Captures Well
- Relative Performance Metric

### Does NOT Capture
- Injury risk directly
- Exercise-specific readiness
- External factors of how the values change

## Global Interpretation Risks

- Datasets operate at different granularities (sets vs days).
- Recovery score is an estimate, not a diagnosis.
- Single-day changes should not drive decisions.
