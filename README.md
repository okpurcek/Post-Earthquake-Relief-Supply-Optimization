# Efficient Post-Earthquake Relief Supply Distribution in Turkey

## Introduction
This project focuses on optimizing the distribution of relief supplies in post-earthquake Turkey. Two different optimization algorithms—**Particle Swarm Optimization (PSO)** and **Mixed-Integer Linear Programming (MILP)**—are applied to minimize transportation costs while ensuring efficient allocation of food, water, and medicine to affected cities. 

Real-world constraints such as fuel shortages, road closures, and varying levels of damage in different cities are incorporated into the model. The results are visualized on maps, and an interactive demand adjustment feature is included to enhance usability.

## Project Objectives
- Develop an optimized relief supply distribution plan using **PSO and MILP**.
- Compare the effectiveness of both algorithms in different scenarios.
- Incorporate **realistic constraints**, such as transportation limitations, fuel availability, and supply-demand disparities.
- Provide **interactive visualization** of supply routes and affected regions.
- Offer insights for emergency response planning and humanitarian logistics.

## Datasets Used
The project utilizes four primary datasets:

### 1️⃣ **Distribution Centers (`distributioncenter.csv`)**
- Contains the locations of major supply centers, their available stock, and population sizes.
- **Key Fields:**
  - `Center`: City where the distribution center is located.
  - `Population`: Total population of the distribution center city.
  - `SupplyFood`, `SupplyWater`, `SupplyMedicine`: Available stock of food, water, and medicine.

### 2️⃣ **Affected Cities (`effectedcities.csv`)**
- Lists cities affected by the earthquake and their estimated demand for relief supplies.
- **Key Fields:**
  - `City`: Name of the affected city.
  - `Population`: Total population of the affected city.
  - `DamageLevel`: Severity of the disaster (High, Moderate, Low).
  - `DemandFood`, `DemandWater`, `DemandMedicine`: Required amount of food, water, and medicine.

### 3️⃣ **Petrol Information (`petrolinformation.csv`)**
- Details the fuel availability and consumption rate per city.
- **Key Fields:**
  - `Center`: City name.
  - `CurrentPetrol(L)`: Total available fuel (in liters).
  - `ConsumptionRate(L/KM)`: Fuel consumption rate per kilometer.

### 4️⃣ **Transport Information (`transportinfo.csv`)**
- Contains data on road and air transport connectivity between cities.
- **Key Fields:**
  - `Source`, `Destination`: City pairs with transport connections.
  - `Distance`: Distance (in km) between the cities.
  - `Transport Road`: Indicates whether road transport is **Open/Closed**.
  - `Road Cost`: Cost of road transportation.
  - `Transport Air`: Indicates whether air transport is **Open/Closed**.
  - `Air Cost`: Cost of air transportation.

## Methodology
### **1️⃣ Data Preprocessing**
- Read and clean CSV datasets.
- Convert numerical values and handle missing data.
- Apply data validation checks.

### **2️⃣ Optimization Models**
#### **Mixed-Integer Linear Programming (MILP)**
- Ensures an **optimal solution** but is computationally expensive for large-scale problems.
- Formulates the problem as a set of linear equations with constraints.
- **Objective:** Minimize total transportation cost while satisfying demand.

#### **Particle Swarm Optimization (PSO)**
- A heuristic optimization method inspired by swarm intelligence.
- Faster than MILP but does not guarantee the global optimal solution.
- Suitable for large-scale problems with real-world constraints.

### **3️⃣ Visualization**
- **Folium maps** are used to illustrate supply routes and affected regions.
- **Color-coded markers** indicate affected cities, distribution centers, and transport routes.
- **Interactive demand sliders** allow dynamic adjustment of needs.

## Installation & Setup
To run this project locally, follow these steps:

### **Prerequisites**
Ensure you have Python installed with the necessary libraries:
```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels pulp folium ipywidgets
```

### **Clone the Repository**
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### **Run the Jupyter Notebook**
Use the following command to launch the Jupyter Notebook and explore the data:
```bash
jupyter notebook YZV202E - Project.ipynb
```

## Project Structure
```
.
|-- data/                       # Data files
|-- README.md                   # Project documentation
|-- yzv202e-report.pdf          # Project report detailing methodology and findings
|-- YZV202E - Project.ipynb     # Jupyter Notebook containing the implementation
|-- LICENSE                     # Project license (MIT License)
```

## Results & Findings
| **Algorithm** | **Pros** | **Cons** |
|--------------|---------------|---------------|
| **MILP** | Guarantees the best possible solution | Slow for large-scale problems |
| **PSO** | Faster and more flexible | May not find the absolute optimal solution |

- **For small-scale problems, MILP is preferable.**
- **For large-scale real-time applications, PSO is more practical.**
- **Some roads are closed, making air transport crucial despite higher costs.**
- **Fuel availability plays a significant role in the feasibility of transport routes.**

## Future Improvements
- **Include real-time data updates** from disaster response agencies.
- **Incorporate machine learning models** to predict supply-demand trends.
- **Extend the model to include alternative transport modes** such as sea and rail.
- **Develop a web-based interactive dashboard** for emergency decision-makers.

## Contributors
- **Oğuz Kağan Pürçek** - Istanbul Technical University

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
