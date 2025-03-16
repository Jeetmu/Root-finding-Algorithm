# Interactive Dashboard for Root Finding & Implied Volatility

This project provides an interactive dashboard that demonstrates several numerical root-finding methods and an implied volatility calculator; all implemented in a Jupyter Notebook. The dashboard is designed to work in environments such as VS Code’s interactive window, Jupyter Notebook, or JupyterLab.

## Table of Contents

- [Project Overview](#project-overview)
- [Folder Structure](#folder-structure)
- [Prerequisites](#prerequisites)
- [Environment Setup](#environment-setup)
  - [Using Python Virtual Environments](#using-python-virtual-environments)
  - [Using Conda (Anaconda/Miniconda)](#using-conda-anacondaminiconda)
- [Installation Instructions](#installation-instructions)
- [Running the Notebook](#running-the-notebook)
- [Features & Enhancements](#features--enhancements)
- [Limitations & Further Enhancements](#limitations--further-enhancements)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Project Overview

This interactive solution demonstrates:
- **Multiple Root-Finding Methods:**  
  Methods include Bisection, Regula Falsi, Newton-Raphson, Secant, Brent's, Halley's, and Müller's methods. In addition, a dedicated function searches for multiple roots within a specified interval.
- **Implied Volatility Calculator:**  
  Using the Black-Scholes call option pricing model, the dashboard employs a Newton-Raphson routine to compute and display the convergence of the implied volatility estimation.

The interactive interface leverages `ipywidgets` to allow users to:
- Input their function \( f(x) \) for root-finding.
- Toggle an option to search for multiple roots.
- Set parameters for computing the implied volatility of options.

## Folder Structure

```
├── .gitignore
├── interactive-dashboard.ipynb
├── original-logic.ipynb
├── README.md
└── requirements.txt (optional)
```

- **.gitignore:** Removes environment specific info setup locally before running (see setup instructions).
- **interactive-dashboard.ipynb:** The main Jupyter Notebook containing the enhanced code and interactive dashboard.
- **original-logic.ipynb:** The original code file used (without the dashboard/interactive interface).
- **README.md:** This file.
- **requirements.txt:** (Optional) A list of required packages for quick setup.

## Prerequisites

Ensure you have the following installed:
- **Python 3.8+**
- **Jupyter Notebook / JupyterLab / VS Code with the Python extension**
- Required Python packages:
  - `numpy`
  - `matplotlib`
  - `sympy`
  - `ipywidgets`
  - `scipy`

You can install the packages using `pip` or `conda` (see below).

## Environment Setup

### Using Python Virtual Environments

1. **Create a Virtual Environment:**
   ```bash
   python -m venv venv
   ```
2. **Activate the Environment:**
   - **Windows (PowerShell):**
     ```bash
     venv\Scripts\activate
     ```
   - **macOS/Linux:**
     ```bash
     source venv/bin/activate
     ```
3. **Install the Required Packages:**
   ```bash
   pip install numpy matplotlib sympy ipywidgets scipy jupyter
   ```
4. **(Optional) Create a `requirements.txt`:**
   ```bash
   pip freeze > requirements.txt
   ```

### Using Conda (Anaconda/Miniconda)

1. **Create a Conda Environment:**
   ```bash
   conda create -n dashboard_env python=3.9
   ```
2. **Activate the Environment:**
   ```bash
   conda activate dashboard_env
   ```
3. **Install the Required Packages:**
   ```bash
   conda install numpy matplotlib sympy ipywidgets scipy jupyter
   ```

## Installation Instructions

1. **Clone or Download the Repository.**
2. **Navigate to the Project Directory:**
   ```bash
   cd path/to/your/project
   ```
3. **Follow the Environment Setup Instructions Above.**

## Running the Notebook

### In VS Code
- **Open VS Code** and install the **Python extension** if not already installed.
- Open the `interactive-dashboard.ipynb` file.
- Use the built-in Jupyter Notebook interface in VS Code (the interactive window) to run cells.
- Click on the **"Update Root Dashboard"** or **"Compute Implied Volatility"** button to generate the convergence plots.

### In Jupyter Notebook or JupyterLab
- Launch Jupyter Notebook:
  ```bash
  jupyter notebook
  ```
- Or launch JupyterLab:
  ```bash
  jupyter lab
  ```
- Navigate to the project folder and open `interactive-dashboard.ipynb`.

## Features & Enhancements

- **Root Finding Methods:**  
  The dashboard includes visual convergence plots for each numerical method, making it easier to compare the speed and accuracy of methods like Bisection, Secant, and Newton-Raphson.
  
- **Multiple Roots Search:**  
  An additional feature to search for and display all roots within a defined interval is provided. This is particularly useful for functions with multiple zero-crossings.

- **Implied Volatility Calculator:**  
  The Black-Scholes model is implemented to compute the implied volatility from a market option price using a Newton-Raphson iterative method. The convergence of the volatility estimation is plotted.

- **Interactive Configuration:**  
  Users can easily switch parameters and observe real-time changes in the plots, offering an intuitive way to experiment with numerical methods and financial calculations.

## Limitations & Further Enhancements

### Limitations:
- **Numerical Convergence:**  
  All root-finding methods rely on initial conditions and tolerances. For functions with poor behavior or multiple nearby roots, some methods may converge slowly or fail.
  
- **Black-Scholes Assumptions:**  
  The implied volatility calculator assumes constant volatility, risk-free rate, and other Black-Scholes conditions. Real market data may exhibit volatility smiles or skewness that are not captured.

### Further Enhancements (Financial Perspective):
- **Enhanced Option Pricing Models:**  
  Incorporate models such as the Heston or SABR models to account for stochastic volatility, better capturing market phenomena like volatility smiles.
  
- **Risk Metrics & Greeks:**  
  Extend the dashboard to compute and visualize option Greeks (Delta, Gamma, Vega, etc.) and other risk measures, providing a more comprehensive view of the option’s behavior.
  
- **Parameter Sensitivity Analysis:**  
  Enable sensitivity analysis to explore how changes in parameters (volatility, interest rate, time to maturity) affect option prices and risk metrics.
  
- **Real Market Data Integration:**  
  Integrate APIs to fetch real-time market data for dynamic calibration of models and more accurate implied volatility estimation.
  
- **Enhanced Visualization:**  
  Provide additional plots and interactive sliders for in-depth analysis and dynamic updates as parameters change.

## Troubleshooting

- **Widgets Not Displaying:**  
  Ensure you are running the notebook in an environment that supports `ipywidgets` (e.g., Jupyter Notebook, JupyterLab, or VS Code’s interactive window).
  
- **Missing Modules:**  
  Verify that all required modules are installed by checking your environment (using `pip list` or `conda list`).

- **Kernel Issues:**  
  If the notebook kernel fails to start or crashes, try restarting the kernel or reinstalling the dependencies.

## License

This project is provided under the [MIT License](LICENSE).

---

### Note on Version Control

It is recommended to include a `.gitignore` file that ignores your virtual environment folder (e.g., `.venv` or `venv`). For example, add the following lines to your `.gitignore`:

```
venv/
.venv/
```

This prevents the virtual environment files from being tracked by Git.