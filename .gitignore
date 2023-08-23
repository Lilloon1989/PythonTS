import pandas as pd
import os

def confirm_compartments(total_compartments):
    compartment_capacities = []
    
    for i in range(total_compartments):
        capacity = float(input("What is the capacity of compartment " + str(i+1) + ": "))
        compartment_capacities.append(capacity)
    
    return compartment_capacities

def confirm_trailer_info():
    thank_you = "Thank you for your information"
    
    trailer_id = input("What is your trailer ID? ")
    print("Your Trailer ID:", trailer_id)
    
    confirm_id = input("Is this correct? Y/N: ")
    if confirm_id == "Y":
        total_compartments = int(input("How many compartments does your trailer have? "))
        print("Your Trailer ID:", trailer_id, "\nTotal Compartments:", total_compartments)
        
        confirm_info = input("Is this information correct? Y/N: ")
        if confirm_info == "Y":
            print(thank_you)
            compartment_capacities = confirm_compartments(total_compartments)
            return trailer_id, total_compartments, compartment_capacities
        elif confirm_info == "N":
            print("Oops! Okay, let's correct the number of compartments.")
            return confirm_trailer_info()
        else:
            print("Please enter Y or N")
            return confirm_trailer_info()
    elif confirm_id == "N":
        print("Okay, let's start over!")
        return confirm_trailer_info()
    else:
        print("Please try again and enter Y or N")
        return confirm_trailer_info()

# Load existing DataFrame if the Excel file exists
excel_file = "Gather_Trailer_Info.xlsx"
if os.path.exists(excel_file):
    existing_df = pd.read_excel(excel_file)
else:
    existing_df = pd.DataFrame()

# Call the function to gather trailer information
trailer_id, total_compartments, compartment_capacities = confirm_trailer_info()

# Create dictionary for DataFrame
new_trailer = {
    "Trailer ID": [trailer_id],
    "Total Compartments": [total_compartments]
}
for i, capacity in enumerate(compartment_capacities, start=1):
    new_trailer[f"Compartment {i}"] = [capacity]

# Append the new trailer information to the existing DataFrame
new_df = pd.DataFrame(new_trailer)
updated_df = pd.concat([existing_df, new_df], ignore_index=True)

# Save the updated DataFrame to an Excel file with a specific sheet name
updated_df.to_excel(excel_file, sheet_name="Trailer Info", index=False)

# Print the updated DataFrame
print(updated_df)
