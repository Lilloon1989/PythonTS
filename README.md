# Trailer Information Management System

The Trailer Information Management System is a Python program designed to help users gather and manage information about trailers and their compartments. The program allows users to input details such as trailer ID, total compartments, and compartment capacities. The gathered information is then stored in a Pandas DataFrame and can be saved to an Excel file for future reference.

## Getting Started

1. **Prerequisites:** Make sure you have Python 3.x installed on your system.

2. **Installation:** Clone this repository or download the program files to your local machine.

3. **Dependencies:** Install the necessary Python libraries by running the following command:

   ```shell
   pip install pandas
   ```

## Usage

1. Run the program by executing the `trailer_info_management.py` script.

   ```shell
   python trailer_info_management.py
   ```

2. Follow the prompts to enter trailer information:
   - Trailer ID
   - Total compartments
   - Compartment capacities

3. Confirm the entered information. If incorrect, you can correct the data.

4. The program will create a Pandas DataFrame with the gathered information and print it to the console.

5. The DataFrame is then saved to an Excel file named "Gather_Trailer_Info.xlsx" in the same directory.

## Appending Trailers

- If the Excel file "Gather_Trailer_Info.xlsx" already exists in the program directory, the program will load the existing data into the DataFrame.
- When you run the program again, you can add new trailers. The new trailer information will be appended to the existing DataFrame.

## Example

Here's an example of how the program works:

1. Enter trailer ID: ABC123
2. Enter total compartments: 3
3. Enter capacity of compartment 1: 1500.0
4. Enter capacity of compartment 2: 2000.0
5. Enter capacity of compartment 3: 1800.0
6. Confirm the information.
7. The program will display the DataFrame and save it to "Gather_Trailer_Info.xlsx".
