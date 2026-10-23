# Manus AI Development Brief: VivaWell Sleep & Lifestyle Intelligence Dashboard

## 1. Project Overview

Build a professional, executive-level **Interactive Lifestyle, Sleep & Wellness Intelligence Dashboard** for VivaWell, a lifestyle, health and wellness company.

The dashboard should transform raw lifestyle and sleep-related data into meaningful visual insights that help users understand patterns across demographics, occupation, sleep quality, stress, physical activity, BMI, blood pressure, heart rate, and sleep disorders.

The goal is to go beyond presenting charts. Develop an analytical tool that tells a clear data story, highlights important patterns, identifies areas that warrant further investigation, and generates practical, evidence-based recommendations.

The dashboard must be intuitive, visually polished, responsive, and accessible to both business executives and users with limited technical or data-analysis experience.

**Important:** Although the dashboard is intended to support business intelligence for VivaWell, the provided dataset does not contain sales or revenue fields. Do not invent sales metrics. Build a lifestyle and wellness intelligence dashboard based on the available data, with insights that may inform future wellness programs, customer segmentation, and service development.

## 2. Brand Identity and Visual Design

Use the attached **VivaWell logo** as the primary reference for the dashboard’s visual identity.

Brand name: VivaWell  
Tagline: “A Healthier, Brighter You”

### Brand colours

Extract and apply a consistent colour palette from the supplied logo:

- **Primary colour:** Deep forest green, used for primary navigation, key headings, and important data elements.
- **Secondary colour:** Natural leaf green, used for secondary series, highlights, and supporting visual elements.
- **Accent colour:** A lighter, fresh green sampled from the logo, used sparingly to highlight meaningful findings or positive indicators.
- **Background:** White or a very light neutral shade to maintain clarity and visual balance.
- **Text:** Dark charcoal or deep green for legibility.

Use the actual logo colours where possible instead of introducing unrelated colours. Define a consistent palette and reuse it across the dashboard.

For charts requiring multiple categories, use coordinated shades of green alongside accessible, muted supporting colours where necessary. Ensure categories remain distinguishable and that warning or adverse indicators are not automatically presented as positive simply because they use green.

### Design direction

The interface should communicate wellness, trust, clarity, professionalism, and evidence-based decision-making.

Use a clean, modern, premium dashboard aesthetic featuring:

- Clear visual hierarchy and restrained use of colour.
- A structured grid layout with consistent spacing and alignment.
- Legible typography and appropriately sized chart labels.
- Clean KPI cards with concise titles and contextual explanations.
- Subtle borders, light shadows, and consistent corner radii.
- Clear navigation between dashboard sections.
- Adequate whitespace to prevent the interface from feeling crowded.
- The VivaWell logo in the header or sidebar without stretching, distorting, or unnecessarily recreating it.

Avoid excessive decoration, oversized charts, unnecessary gradients, cluttered legends, and ornamental graphics that compete with the information.

The dashboard should feel like a professional analytics product, not a generic template or marketing landing page.

## 3. Data Source and Upload Requirements

The initial dataset is an Excel worksheet or table named:

`cleaned_sleep_lifestyle_data`

The dataset contains the following fields:

- Person ID
- Gender
- Age
- Age Group
- Occupation
- Sleep Duration
- Quality of Sleep
- Physical Activity Level
- Stress Level
- BMI Category
- Blood Pressure
- Heart Rate
- Daily Steps
- Sleep Disorder

Treat these names as the expected schema, while allowing for harmless differences in capitalization, spacing, and formatting.

### Mandatory local file upload functionality

Build a functional file-upload feature into the dashboard so users can select a dataset directly from their local computer through the webpage.

The application must not depend on a single hard-coded dataset or require the developer to manually replace a file whenever new data becomes available.

Support, at minimum:

- Excel workbooks (`.xlsx`).
- CSV files (`.csv`).

The uploaded file should be the source of truth for all displayed metrics, visualizations, filters, statistical calculations, and recommendations.

### File upload workflow

1. Display a clearly visible upload area with a button labelled **“Upload Dataset”** and an optional drag-and-drop zone.
2. Allow the user to select a local Excel or CSV file.
3. For Excel workbooks, identify available worksheets and tables. Prefer `cleaned_sleep_lifestyle_data` when present. If it is absent, identify worksheets with matching column headers and allow the user to select the appropriate one.
4. Validate the selected dataset before rendering the dashboard.
5. Display a summary of the imported data, including the number of records, number of fields, successfully matched columns, missing values, and any validation warnings.
6. If column names differ slightly, attempt safe, transparent matching. If a required field is missing or ambiguous, provide a clear message and a way to map the file's columns to the expected fields.
7. Once validation succeeds, automatically refresh all dashboard components using the uploaded data.
8. Provide an option to upload another dataset or replace the current one.
9. Display a clear empty state before a dataset is loaded, with instructions explaining how to get started.

If validation fails, explain the problem in plain language and indicate how to resolve it. Never silently omit essential fields, substitute fabricated values, or display misleading visualizations.

### Privacy and data handling

Treat the dataset as potentially sensitive because it contains person-level health and lifestyle information.

Where technically feasible, perform file parsing and analysis locally in the browser. Do not transmit uploaded data to external services, retain it in persistent storage, or expose person-level information unnecessarily.

If local-only processing is not feasible, disclose the actual data-handling requirements clearly before upload. Do not claim that processing is local or private unless the implementation genuinely provides those protections.

## 4. Analytical Objectives and Business Questions

Organize the dashboard around the following analytical questions. Each question should be answered with an appropriate visualization, supporting metrics, and a concise explanation of the observed findings.

All calculations and narrative insights must update dynamically when a new dataset is uploaded or dashboard filters change.

### Analysis 1: Gender Distribution

**Business question:** What is the distribution of observations across gender?

Analyze the number and proportion of records in each gender category.

Recommended visualization:
- A donut chart or a clean horizontal bar chart showing the count and percentage for each category.

Supporting metrics:
- Total records.
- Count per gender category.
- Percentage of the total represented by each category.

Show category labels and values clearly. Handle missing or unspecified gender values transparently rather than silently excluding them.

The accompanying insight should identify the largest and smallest represented groups, where applicable, and explain any relevant limitations arising from an uneven sample distribution.

### Analysis 2: Blood Pressure by BMI Category

**Business question:** Does blood pressure vary across BMI categories?

Examine the distribution of blood pressure values across the available BMI categories.

Recommended visualizations:
- A box plot or another suitable distribution chart comparing blood pressure across BMI categories.
- A supporting chart or table showing sample sizes and summary statistics for each category.

Where blood pressure is supplied in a format such as `120/80`, parse the systolic and diastolic values into separate analytical fields when the format allows reliable extraction.

Analyze systolic and diastolic pressure separately rather than treating the combined blood pressure string as a numerical value.

Where appropriate, display mean or median systolic and diastolic values, variability, and record counts by BMI category.

Do not assume that BMI category or blood pressure values conform to particular clinical thresholds without first examining the dataset and establishing that the values can be interpreted reliably.

Explain any visible differences between categories without claiming that BMI causes changes in blood pressure. Note that differences may be influenced by sample composition or other unmeasured factors.

### Analysis 3: Age Group Comparison — Stress, Physical Activity and Sleep Quality

**Business question:** Which age groups exhibit the highest stress levels, physical activity, and sleep quality?

Compare age groups across three dimensions:

1. Stress level.
2. Physical activity level.
3. Quality of sleep.

Recommended visualization:
- A heatmap or aligned small-multiple charts comparing age groups across the three measures.
- Supporting bar charts, where appropriate, showing the average value for each age group.

Display sample size alongside each age group so that results based on small groups are not misleading.

Use separate scales or appropriately labelled charts when the metrics have different measurement ranges. Do not combine unrelated metrics into a single average or composite score without a clearly defined and defensible methodology.

Before calculating averages, inspect the data types and distributions. If physical activity level is categorical or ordinal rather than a continuous numerical measure, use category distributions, proportions, or another appropriate summary instead of an unqualified numerical average.

The dashboard should clearly identify:

- Which age group has the highest observed stress level.
- Which age group has the highest observed physical activity.
- Which age group has the highest observed sleep quality.
- Any meaningful differences or patterns between age groups.

Distinguish observed group averages from individual experiences and avoid interpreting associations as evidence of causation.

### Analysis 4: Occupation, Stress, Sleep Quality and BMI

**Business questions:**

- How do stress levels vary across occupations?
- How does sleep quality vary across occupations?
- Are some occupations associated with particular BMI categories?
- Which occupations have the highest or lowest observed stress and sleep quality?

Analyze occupation as a potentially useful segmentation variable.

Recommended visualizations:

- A ranked horizontal bar chart showing average stress level by occupation.
- A separate chart comparing sleep quality across occupations.
- A stacked bar chart showing the distribution of BMI categories within each occupation.
- A heatmap summarizing occupation-level differences across stress, sleep quality, and BMI category proportions.

Show record counts for each occupation and make the charts sortable.

Where appropriate, allow users to examine individual measures by selecting an occupation.

For BMI analysis, show both within-occupation percentages and record counts so that occupations with larger samples do not dominate interpretation simply because they have more records.

Identify occupations with notable patterns, but do not assume that occupation itself causes higher stress, poorer sleep, or a particular BMI category. Clearly label the findings as observed associations.

Where sample sizes are too small for reliable comparisons, show a warning or suppress strong narrative conclusions.

### Analysis 5: Heart Rate and Physical Activity

**Business question:** Is there a relationship between heart rate and physical activity level?

Explore whether recorded heart rate varies with physical activity.

Select the visualization based on the actual data structure.

If physical activity level is numerical:
- Use a scatter plot with physical activity on the x-axis and heart rate on the y-axis.
- Where appropriate, include a trend line.
- Display a relevant correlation coefficient and the number of valid observations.

If physical activity level is categorical or ordinal:
- Compare heart rate distributions across activity categories using box plots or another appropriate distribution visualization.
- Display group sizes and suitable summary statistics.

Use an appropriate correlation method based on the measurement scales and data distribution. If reporting a correlation coefficient, explain its direction and approximate strength in plain language.

Do not imply that the observed relationship establishes causation, that a higher heart rate is automatically unhealthy, or that the recorded activity measure reflects a specific level of exercise intensity unless the dataset supports that interpretation.

Clearly indicate whether conclusions are limited by missing data, restricted variation, or small sample sizes.

### Analysis 6: Sleep Disorders, Sleep Duration and Sleep Quality

**Business question:** How do recorded sleep disorders relate to sleep duration and overall sleep quality?

Compare sleep duration and quality across the available sleep disorder categories.

Recommended visualizations:

- A box plot comparing sleep duration across sleep disorder categories.
- A separate box plot or distribution chart comparing sleep quality across the same categories.
- A supporting summary table showing record counts, median values, averages where appropriate, and missing values.

Where the dataset includes a category representing no sleep disorder, compare it with the recorded disorder categories. Do not assume that a blank value means no sleep disorder.

Distinguish explicitly between:
- A genuine category indicating no recorded disorder.
- A missing or unknown sleep disorder value.

Identify which groups exhibit comparatively shorter sleep duration or lower sleep quality in the available sample.

Explain the magnitude and consistency of observed differences where supported by the data. Avoid unsupported clinical diagnoses, treatment advice, or causal claims.

## 5. Executive Overview Page

Create an executive overview that allows users to understand the dataset and its most important findings at a glance.

### KPI cards

Where the required fields and valid observations are available, include:

- **Total Records Analysed:** Number of valid person-level records included.
- **Average Sleep Duration:** Mean sleep duration, with appropriate units.
- **Average Sleep Quality:** Mean recorded sleep-quality score.
- **Average Stress Level:** Mean recorded stress score.
- **Average Heart Rate:** Mean recorded heart rate, with appropriate units.
- **Sleep Disorder Prevalence in the Dataset:** Percentage of valid, explicitly classified records with a recorded sleep disorder, if the categories and denominators support this calculation.

For each KPI, show a clear label, the calculated value, and a short explanatory caption where helpful.

Do not treat these metrics as sales KPIs or imply that they represent the entire population. Describe them as statistics from the uploaded dataset.

Only display metrics that can be calculated reliably. If a field is absent or unusable, explain why the relevant metric cannot be shown rather than inventing a substitute.

### Executive insight summary

Above or alongside the main visualizations, create a dynamic **“Key Findings”** section containing approximately three to five of the most important insights identified from the currently loaded dataset.

Each finding should include:
- A clear headline.
- The observed pattern.
- A relevant numerical value, percentage, or comparison when available.
- A brief explanation of why the finding matters.
- A practical follow-up action or question for investigation.

Prioritize insights according to their analytical relevance, magnitude, and reliability, not merely the size of the difference.

These findings must be generated from actual calculations. They must change when another dataset is uploaded or when filters are applied. Never hard-code findings, statistics, rankings, or recommendations.

## 6. Dashboard Structure and Navigation

Organize the dashboard into the following sections or tabs.

### Page 1: Executive Overview

Present the KPI cards, key findings, demographic snapshot, and selected high-level wellness patterns.

The user should quickly understand the size and basic composition of the dataset, the overall recorded sleep and stress measures, and the most notable findings.

### Page 2: Demographics and Lifestyle

Include:
- Gender distribution.
- Age group distribution.
- Physical activity comparisons.
- Daily steps distribution.
- Other relevant lifestyle patterns supported by the available fields.

Daily steps should be used to enrich the analysis, not to make unsupported conclusions about health status or exercise intensity.

### Page 3: Sleep and Health

Include:
- Sleep duration and quality.
- Sleep disorder comparisons.
- Blood pressure by BMI category.
- Heart rate and physical activity relationships.

Use clear section headings that explain the analytical question being answered.

### Page 4: Occupational Insights

Include:
- Stress levels by occupation.
- Sleep quality by occupation.
- BMI category distribution by occupation.
- An integrated view of occupational patterns.

Prioritize charts that make comparisons easy, even when there are many occupation categories.

### Page 5: Data Explorer and Quality

Provide a searchable, sortable view of the uploaded dataset or an appropriate analytical table.

Include a data-quality summary showing missing values, duplicate records, data-type issues, invalid values, and other relevant quality checks.

Retain Person ID only where necessary for identifying records during exploration. Avoid exposing individual-level information in the executive overview or generated recommendations.

Ensure that the interface makes it clear which rows were included in each analytical calculation.

## 7. Interactive Features

The dashboard must be genuinely interactive, not a static report.

Implement the following functionality:

### Global filters

Provide intuitive filters for:
- Gender.
- Age Group.
- Occupation.
- BMI Category.
- Sleep Disorder.

Include an age-range filter where the data supports it.

Filters should allow users to explore specific population segments. All relevant KPI cards, charts, sample sizes, and generated insights must update consistently when filters change.

Do not introduce date filters because the specified schema does not include a date field.

### Chart interactions

Where technically appropriate, support:
- Hover tooltips with category names, values, percentages, and sample sizes.
- Sorting charts by numerical values.
- Clicking chart categories to filter or cross-highlight related charts.
- Drill-down into relevant categories.
- Switching between relevant measures or chart views.
- Clear chart titles, legends, labels, units, and explanatory tooltips.

### Filter management

Include:
- A clearly visible filter panel.
- A **“Reset Filters”** control.
- A **“Clear Dataset”** or equivalent action that safely returns the interface to its initial state.
- An indication when filters are active.

Make sure resetting filters restores the correct baseline calculations for the currently uploaded dataset without requiring a page reload.

### Export functionality

Where technically feasible, allow the user to:
- Download an executive summary of the current analysis.
- Export key findings and aggregated analytical tables.
- Export a filtered dataset through an explicit user-initiated action, with a clear privacy warning.

Ensure that exports reflect the currently selected dataset and filters. Never include fabricated metrics or stale results in exported files.

## 8. Data Processing, Validation and Statistical Integrity

The dashboard must include a reliable data-processing layer that prepares the uploaded dataset for analysis.

### Data preparation

- Normalize column names without changing their meaning.
- Detect and handle inappropriate data types.
- Convert numerical measures to numeric values only when conversion is valid.
- Standardize category labels where safe and transparent.
- Identify missing, duplicate, inconsistent, or invalid records.
- Validate numeric ranges and flag suspicious values instead of automatically assuming they are correct.
- Preserve the original uploaded values where appropriate so that data cleaning decisions remain traceable.

Do not automatically delete every row with a missing value. Use the valid observations available for each analysis, and clearly display the resulting sample size and limitations.

Do not confuse a missing value with zero, an unknown category with a genuine category, or an absence of a recorded disorder with confirmed absence of a disorder.

### Metric definitions

Define the calculation method for each KPI and chart. Use consistent denominators when calculating proportions.

Where a chart excludes records because a required field is missing, disclose the number of valid observations used.

Use means where useful, but consider medians and distributions when data are skewed or contain outliers.

When comparing groups, present sample sizes and avoid strong conclusions based on very small groups.

For correlation analysis, select an appropriate statistical measure based on the variables' measurement scales. Do not report a correlation when there are insufficient valid observations or no meaningful variation.

Do not apply arbitrary clinical thresholds, invent statistical significance, or use causal language that cannot be justified by the data.

Where statistical tests are used, explain their purpose and limitations. Statistical significance alone should not determine whether a result is operationally meaningful.

### Data-quality indicators

Include useful checks for:
- Missing values by field.
- Duplicate Person IDs or potential duplicate records.
- Invalid or non-numeric values in numerical fields.
- Unexpected category labels.
- Unparseable blood pressure values.
- Sample sizes that may be too small for meaningful comparisons.

Do not automatically assume that every repeated Person ID is a duplicate record. Identify potential duplicates and make the limitation visible.

## 9. Insight Generation and Actionable Recommendations

A central purpose of this dashboard is to turn descriptive analysis into useful next steps.

For every major analytical section, include a concise interpretation of the results and a practical recommendation or follow-up question.

Recommendations must be grounded in observed patterns within the uploaded dataset.

Examples of the required approach include:

- If a particular age group shows comparatively high recorded stress, recommend investigating that group's needs and relevant contextual factors before proposing a targeted wellness initiative.
- If some occupations show lower recorded sleep quality, suggest examining workplace routines, schedules, or other contextual factors rather than assuming the occupation is the cause.
- If sleep disorder categories differ in recorded sleep duration or quality, highlight those differences and explain where further investigation may be useful.
- If heart rate differs across physical activity categories, describe the observed relationship without equating it with a clinical health assessment.

These are examples of how to frame recommendations, not conclusions to display regardless of the data.

For each recommendation, indicate:
- **Finding:** What the data shows.
- **Evidence:** The relevant value, difference, or percentage.
- **Implication:** Why this may matter to VivaWell.
- **Recommended next step:** What should be investigated, tested, or considered.

Where the data is insufficient to justify a recommendation, state that clearly.

Avoid generic advice that could have been written without analyzing the dataset. Do not invent customer preferences, commercial demand, sales opportunities, or population-wide health conclusions from this dataset alone.

## 10. User Experience and Accessibility

Build an interface that is intuitive for business users who may not have advanced data-analysis skills.

The dashboard should:
- Be responsive across desktop, tablet, and mobile screen sizes.
- Use plain-language chart titles and explanations.
- Avoid unexplained technical jargon.
- Display clear loading, success, empty, and error states.
- Provide helpful tooltips for technical terms.
- Use accessible text contrast, readable typography, and meaningful chart labels.
- Preserve appropriate spacing and visual hierarchy at different screen sizes.
- Avoid overwhelming the user with too many charts on a single screen.

Use progressive disclosure: present the most important findings first and allow users to explore more detailed analysis when needed.

## 11. Implementation Expectations

Build a functional, data-driven web application with a clear separation between:
- File upload and validation.
- Data transformation and calculation.
- Dashboard state and filtering.
- Visualizations.
- Insight generation.
- Export functionality.

Use a reliable charting approach that supports the visualizations described above and maintains consistency across the dashboard.

Ensure every interactive control works as expected. Do not create decorative buttons that have no functionality.

All charts must use actual values calculated from the selected dataset. Do not populate the dashboard with mock data after a real dataset has been uploaded.

Make the dashboard reusable so a user can upload another compatible dataset without rebuilding the application.

If the selected file contains a different schema, provide clear feedback about missing or ambiguous required fields rather than allowing calculations to fail silently.

The resulting interface should work as a complete analytical experience, not merely as a visual prototype.

## 12. Required Deliverables

Deliver the following:

1. **A working interactive dashboard** with the VivaWell branding and the analytical sections described above.
2. **A functional local file-upload workflow** supporting Excel and CSV datasets.
3. **Dynamic analytical calculations and visualizations** driven by the currently uploaded data.
4. **Contextual findings and actionable recommendations** derived from actual results.
5. **A data-quality and validation view** that explains missing values, exclusions, and other relevant limitations.
6. **Working filters, chart interactions, and dataset replacement functionality.**
7. **Export functionality** for analytical summaries and aggregated results where technically supported.
8. **Clear instructions for using the dashboard**, including supported file formats and expected column names.

## 13. Acceptance Criteria and Final Testing

Before considering the dashboard complete, verify the following:

- The supplied VivaWell logo is incorporated appropriately and the visual theme matches its colours.
- The dashboard opens in a clear initial state and explains how to upload a dataset.
- A valid Excel workbook containing `cleaned_sleep_lifestyle_data` can be uploaded and analyzed.
- A compatible CSV file can also be uploaded.
- Alternative worksheet names and minor column-name variations are handled transparently.
- Missing required columns trigger clear, actionable validation messages.
- Every KPI, chart, filter, and insight uses the actual selected dataset.
- All six core analytical questions are addressed by appropriate visualizations and interpretations.
- The global filters work consistently across relevant dashboard components.
- Numerical calculations handle missing values and data types correctly.
- Blood pressure is not treated as a single numerical value when it is recorded as a combined systolic/diastolic string.
- Missing sleep disorder information is not automatically classified as absence of a disorder.
- Small sample sizes and important analytical limitations are disclosed where relevant.
- Correlation and group comparisons are not presented as proof of causation.
- Uploading a replacement dataset refreshes the dashboard without retaining stale metrics or insights from the previous file.
- Exported summaries reflect the current data and filters.
- Layouts, charts, labels, and controls remain usable on smaller screens.
- The dashboard does not display fabricated findings or claim that unsupported analyses have been completed.

### Final Direction

Prioritize analytical accuracy, executive-level clarity, visual consistency, and usability.

The finished product should enable a VivaWell user to upload a dataset, explore the underlying lifestyle and wellness patterns, understand what the data reveals, identify areas that deserve attention, and determine practical next steps.

**Build the functional dashboard, validate the analytical workflows, and ensure that the complete experience works with a real uploaded dataset. Do not stop at a mock-up or a static visual demonstration.**