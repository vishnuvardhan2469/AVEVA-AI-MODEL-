# AI-Driven Manufacturing Intelligence (Option B: Optimization Engine)

This project provides an AI-driven framework that dynamically optimizes energy consumption and carbon emissions at the batch level while maintaining production quality and yield in manufacturing systems.

## Solution Architecture

The solution consists of four main components designed to solve the problem of batch-level variability:

1. **`data_pipeline.py`**: Aggregates time-series batch data and merges configuration parameters to provide a unified data source.
2. **`surrogate_model.py`**: A Random Forest machine learning model trained to predict Yield, Quality, and Energy metrics based on configuration inputs. Due to the limited overlapping data points in the provided sample dataset, an intelligent synthetic data augmentation engine is used to train a robust simulation model.
3. **`optimization_engine.py`**: Uses `SciPy` (`SLSQP`) to find the **Golden Signature**—a Pareto-optimal machine configuration that minimizes energy use while penalizing quality degradation.
4. **`app.py`**: A **Streamlit** Web Application that provides real-time "Human-in-the-loop" decision support. It lets operators adjust priority weights (Energy vs. Quality) and instantly recalculates and recommends the new Golden Signature.

## Getting Started

### Prerequisites

- Python 3.9+
- A Virtual Environment is highly recommended.

### Installation

1. Create a virtual environment:
   ```bash
   python -m venv venv
   ```
2. Activate the virtual environment:
   - On Windows (PowerShell):
     ```bash
     .\venv\Scripts\Activate.ps1
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```
3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Execution

1. **Train the Surrogate Model** (Only required once, to generate the `.joblib` model file):
   ```bash
   python surrogate_model.py
   ```
2. **Run the Streamlit Dashboard Demo**:
   ```bash
   streamlit run app.py
   ```

A browser window will automatically open with the Interactive Optimization Engine UI at `http://localhost:8501`.
