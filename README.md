# telecom-query-pipeline
ython-based data analysis project for processing and extracting insights from telecommunications datasets using Pandas.
import pandas as pd
import numpy as np

def load_and_analyze_data(file_path):
    """Loads telecom dataset and performs basic analysis using pandas."""
    try:
        df = pd.read_csv(file_path)
        print(f"Dataset loaded successfully with {df.shape[0]} rows and {df.shape[1]} columns.")
        
        # Example using the .query() method for data filtering
        # Modify the query based on your specific telecom columns (e.g., 'MonthlyCharges', 'Contract')
        if 'MonthlyCharges' in df.columns:
            high_value_customers = df.query("MonthlyCharges > 70.0")
            print(f"Filtered {len(high_value_customers)} high-value customers.")
            return high_value_customers
        
        return df
    except FileNotFoundError:
        print(f"Error: The file {file_path} was not found.")
    except Exception as e:
        print(f"An error occurred: {e}")

if __name__ == "__main__":
    # Replace 'telecom_data.csv' with your actual dataset file path
    print("Running Telecom Data Analysis Script...")
    # df = load_and_analyze_data('telecom_data.csv')
