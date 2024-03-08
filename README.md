# Invoice-Correction-Automation# Import necessary libraries
import pandas as pd

# Load the raw data
invoice_data = pd.read_csv("invoice_data.csv")

# Define function to automate invoice corrections
def automate_invoice_corrections(invoice_data):
    # Apply corrections based on predefined rules
    invoice_data['Corrected_Amount'] = invoice_data['Invoice_Amount'] * 0.95  # Applying 5% discount for corrections
    
    # Update status column to indicate corrections made
    invoice_data['Status'] = 'Corrected'
    
    # Save corrected data to a new file or database table
    invoice_data.to_csv("corrected_invoice_data.csv", index=False)
    
    return invoice_data

# Call the function to automate invoice corrections
corrected_invoice_data = automate_invoice_corrections(invoice_data)

# Display the corrected invoice data
print(corrected_invoice_data)
