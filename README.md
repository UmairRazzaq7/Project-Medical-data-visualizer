# 🩺 Medical Data Visualization Project

This project explores and visualizes a medical dataset to uncover patterns related to cardiovascular disease using Python libraries such as Pandas, Seaborn, and Matplotlib.

## 📊 Objective

The goal of this project is to:
- Clean and preprocess real-world medical data.
- Perform categorical analysis of risk factors such as cholesterol, glucose levels, smoking, alcohol consumption, physical activity, and obesity.
- Visualize how these factors vary between individuals *with* and *without* cardiovascular disease.

## 📁 Dataset

The dataset contains anonymized patient health data, including the following columns:

- cardio: Presence (1) or absence (0) of cardiovascular disease.
- cholesterol: Categorical cholesterol level (1 = normal, 2 = above normal, 3 = well above normal).
- gluc: Categorical glucose level (1 = normal, 2 = above normal, 3 = well above normal).
- smoke: 1 if the patient smokes, 0 otherwise.
- alco: 1 if the patient consumes alcohol, 0 otherwise.
- active: 1 if the patient is physically active, 0 otherwise.
- overweight: 1 if the patient is overweight, 0 otherwise.

## 🛠 Tools & Libraries

- Python
- Pandas
- Seaborn
- Matplotlib
- Jupyter Notebook

## 🔄 Data Transformation

The dataset was reshaped using pd.melt() to convert wide-format risk factors into long-format for categorical plotting. This format allowed side-by-side comparison between patients with and without cardiovascular disease.

```python
df_melted = pd.melt(
    df,
    id_vars=['cardio'],
    value_vars=['cholesterol', 'gluc', 'smoke', 'alco', 'active', 'overweight'],
    var_name='variable',
    value_name='value'
)

📈 Visualization

Categorical plots (catplot) were created to show the count distribution of each health factor grouped by cardiovascular disease status:

sns.catplot(data=df_melted, x='variable', hue='value', col='cardio', kind='count')

This clearly illustrates how unhealthy factors (like high cholesterol or lack of activity) are more common in patients with heart disease.

🔍 Key Insights

High cholesterol and glucose levels are more prevalent in individuals with cardiovascular disease.

Lifestyle habits such as smoking, alcohol consumption, and lack of physical activity are associated with higher heart disease risk.

Being overweight is common in both groups but more concentrated among those with heart disease.


🧾 Conclusion

This project demonstrates how medical data can be explored and visualized to uncover meaningful health patterns. By transforming and analyzing the data effectively, we can better understand how certain lifestyle and biological risk factors relate to cardiovascular disease. Visual analytics not only highlight these relationships but also support more informed health decisions and deeper insights for future research.