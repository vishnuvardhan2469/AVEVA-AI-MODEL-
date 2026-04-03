# AVEVA Golden Signature Engine 🏭⚡

An AI-driven digital twin and optimization engine that generates "Golden Signatures" for manufacturing parameter generation. It balances energy reduction, strict quality control, and production yield dynamically in real-time.

## 🎯 Project Overview
This project provides an AI-driven framework that dynamically optimizes energy consumption and carbon emissions at the batch level while maintaining production quality and yield. By using predictive surrogate modeling and global optimization algorithms, it simulates physical operations to prescribe actionable parameter adjustments.

## 🧠 System Architecture
The solution consists of four core micro-components designed to solve non-linear manufacturing problems:

1. **`data_pipeline.py`**: Aggregates time-series batch data and merges configuration parameters to provide a unified telemetry data source.
2. **`surrogate_model.py`**: A Random Forest machine learning model trained to predict Yield, Quality, and Energy metrics based on configuration inputs. Uses an intelligent synthetic data augmentation engine to simulate wide parameter search spaces securely without real-world risk.
3. **`optimization_engine.py`**: Uses `SciPy` (`dual_annealing`) for global optimization to discover the **Golden Signature**—a Pareto-optimal machine configuration that minimizes energy use, ensures high yield, and heavily penalizes quality degradation.
4. **`app.py`**: A **Streamlit** Web Application providing real-time "Human-in-the-loop" decision support. It features interactive topography, explainable AI (SHAP) insights, and agentic workflows for plant approval.

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Activated Virtual Environment

### Installation
1. Apply a virtual environment and activate it:
   ```bash
   python -m venv venv
   # Windows
   .\venv\Scripts\Activate.ps1
   # macOS/Linux
   source venv/bin/activate
   ```
2. Install the necessary dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Execution
1. **Train the Surrogate Model** (Generates the `.joblib` model artifact):
   ```bash
   python surrogate_model.py
   ```
2. **Run the Application**:
   ```bash
   streamlit run app.py
   ```
3. A browser window will automatically launch the **Interactive Optimization Dashboard** at `http://localhost:8501`.

## 📸 Core Capabilities

### 1. Global Optimization Hub
Set priorities for energy, quality, or yield to drive the optimization engine.
![Global Optimization Hub](images/setup.png)

### 2. Predictive Impact Analysis
Review projected outcomes against baseline performance and monitor total order carbon avoidance.
![Predictive Impact Analysis](images/outcomes.png)

### 3. Explainable AI (XAI)
Visualize SHAP value relative feature importance dynamically.
![Explainable AI (XAI)](images/xai_analysis.png)

### 4. 3D Pareto Frontier
Map the "Golden Signature" inside a multi-dimensional topography cloud of simulated outcomes.
![3D Pareto Frontier](images/pareto_frontier.png)

### 5. Agentic Workflows
Auto-calculate compliance checking, track predictions, and print PDF executive reports for production runs.
![Agentic Workflows](images/agent_workflow.png)
