# Road Accident Data Analysis

## Project Overview

This project performs exploratory data analysis (EDA) on a road accident dataset using Python. The analysis focuses on understanding the structure and quality of the data, preparing variables for analysis, and visualizing important accident-related patterns.

The notebook used for the analysis is `gdgTask.ipynb`, and the dataset referenced by the notebook is `Dataset_1.csv`.

## Dataset

The dataset contains **201,020 records and 48 columns** after duplicate removal.

The variables cover several aspects of road accidents, including:

- Accident date and time
- State and district
- Urban/rural area type
- Geographic coordinates
- Road type and road condition
- Road lighting and number of lanes
- Speed limits and estimated speed
- Junction and traffic-signal information
- Weather, visibility, temperature, and rainfall
- Driver age, gender, and driving experience
- License status
- Alcohol, distraction, mobile-phone use, and fatigue
- Helmet/seatbelt usage
- Vehicle type, age, brand, and model
- Vehicle condition and overloading
- Primary and secondary accident causes
- Emergency-service response
- Injuries, fatalities, and hospitalization
- Accident severity
- Insurance claims and claim amount

## Analysis Workflow

### 1. Data Loading

The notebook loads the dataset with Pandas:

```python
df = pd.read_csv("Dataset_1.csv")
```

The dataset shape and column names are inspected.

### 2. Duplicate Removal

Duplicate records are removed using:

```python
df.drop_duplicates(inplace=True)
```

The resulting dataset remains **201,020 rows × 48 columns**.

### 3. Missing-Value Handling

Missing numerical values are filled using the **mean** for variables such as:

- Latitude and longitude
- Speed limit
- Visibility
- Temperature
- Driver age
- Driving experience
- Vehicle age
- Response time
- Insurance claim amount

Categorical/mixed variables are filled using the **most frequent value**, including weather condition, junction type, vehicle information, district, traffic-signal information, and other categorical fields.

### 4. Categorical Encoding

Several binary variables are converted into numerical representations. For example:

- `median_present`
- `traffic_signal_present`
- `mobile_phone_used`

Other categorical columns are encoded using `LabelEncoder`, including:

- `hospitalization_required`
- `road_lighting`
- `emergency_services_called`
- `ambulance_called`
- `police_called`
- `insurance_claim_filed`

### 5. Exploratory Data Visualization

The notebook creates visualizations for the following areas:

#### Accident Severity Distribution
A bar chart shows the distribution of accidents across:

- Fatal
- Severe
- Moderate
- Minor

#### Primary Causes of Accidents
A horizontal bar chart visualizes accident counts by primary cause, including causes such as:

- Signal Violation
- Poor Visibility
- Poor Road Condition
- Driver Fatigue
- Pedestrian Error
- Drunk Driving
- Distracted Driving
- Weather
- Wrong-Side Driving
- Mechanical Failure
- Overspeeding
- Animal Crossing
- Other

#### Injuries vs Fatalities
A scatter plot examines the relationship between the number of injuries and fatalities in individual accidents.

#### Accidents by Road Condition
A bar chart compares accidents across road conditions such as:

- Dry
- Wet
- Pothole-Ridden
- Under Construction
- Loose Surface

#### Accidents by Vehicle Type
A bar chart compares accident counts for different vehicle types, including:

- Two-Wheeler
- Car
- Truck
- Pedestrian
- Auto-Rickshaw
- Bus
- Bicycle
- Tractor

#### Accidents by Driver Gender
A bar chart presents accident counts by driver gender.

## Conclusion

This project provides an initial exploratory analysis of a large road accident dataset. It combines data cleaning, missing-value treatment, categorical encoding, and visual exploration to prepare the dataset for more advanced statistical analysis and machine-learning applications.
