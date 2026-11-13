# Satellite Imagery Disaster Damage Analysis

**DATA C200 Graduate Project — UC Berkeley**

Exploratory analysis of post-disaster satellite imagery to understand whether building damage severity can be distinguished from visual features, as groundwork for a damage-classification model.

## Question

Do satellite image tiles of buildings with different damage levels (no damage → destroyed) differ measurably in their visual properties, and how does this vary across disaster types?

## Data

Satellite image tiles from three disaster events, each labeled with a building damage level:

| Event | Training images | Labels |
|---|---|---|
| Midwest flooding | 200 | 0–3 |
| SoCal fire | 200 | 0–3 |
| Hurricane Matthew | 200 | 0–3 |

Damage levels: `0` No Damage · `1` Minor · `2` Major · `3` Destroyed

**Source:** [ADD DATASET NAME AND LINK]

The data is not included in this repo because of its size. To reproduce:

1. Download `satellite-image-data.zip` from the source above.
2. Place it in a folder in your Google Drive.
3. Open the notebook in Colab and set `project_folder_path` in the config cell to that folder.

## What's in the notebook

1. **Data loading:** unzips the data and loads train/test image arrays and labels
2. **Data cleaning:** reshapes the images into a tabular feature set (mean R/G/B, brightness), then checks for missing and out-of-range values
3. **EDA:** summary statistics overall, by disaster category, and by damage level
4. **Figures:**
   - Fig 1: Label distribution per category (shows heavy class imbalance)
   - Fig 2: Sample tiles by category and damage level
   - Fig 3: RGB pixel intensity distributions by category
   - Fig 4: Mean RGB intensity by damage level
   - Fig 5: Feature correlation heatmap

## Key findings so far

- **Severe class imbalance:** Minor and Major damage are rare in every category (e.g., SoCal fire has 2 Minor and 1 Major out of 200), which will shape model choice and evaluation.
- **Damage distributions differ by event:** flooding is mostly undamaged, fire is mostly destroyed, and hurricane damage is more spread out.
- **Destroyed buildings are darker on average:** mean brightness drops from about 82 (Minor) to about 72 (Destroyed), but simple color features alone are unlikely to separate the classes well.

## Tools

Python · NumPy · pandas · matplotlib · seaborn · Google Colab

## Team

[ADD TEAM MEMBER NAMES]
