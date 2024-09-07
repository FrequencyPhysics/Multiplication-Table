Multiplication Table Generator
Overview
This Bash script generates a multiplication table based on user input. It allows the user to specify a number and choose whether they want the table in ascending or descending order. The script also handles invalid input by prompting the user to try again.

Script Details
Functionality
Prompt for Number: The script asks the user to enter a number.
Prompt for Order: The user is then asked to choose the table order:
Ascending [a]
Descending [d]
Generate Multiplication Table:
Descending Order: Uses a list form for loop.
Ascending Order: Uses a C-style for loop.
Handle Invalid Input: If the user inputs anything other than 'a' or 'd', the script will prompt them to retry.
Bash Script
bash
Copy code
#!/bin/bash

# Bash script for Generating a Multiplication Table

# Asks the user to enter a number
read -p "Enter a number: " num

# Asks the user to choose the table order (ascending or descending)
read -p "Would you like the table in ascending [a] or descending [d] order? " user

# Checks if user wants the table in descending order
if [ "$user" == "d" ]; then
    echo "Multiplication table for $num in descending order:"
    # List form for loop to generate multiplication table from 10 to 1
    for i in {10..1}; do
        result=$((num * i)) # Perform multiplication
        echo "$num x $i = $result" # Print result
    done

# Checks if the user wants the table in ascending order
elif [ "$user" == "a" ]; then
    echo "Multiplication table for $num in ascending order:"
    # C-style for loop to generate multiplication table from 1 to 10
    for ((i = 1; i <= 10; i++)); do
        result=$((num * i)) # Perform multiplication
        echo "$num x $i = $result" # Print result
    done

# Else statement to handle invalid user input
else
    echo "Invalid value, Please retry" # Informs the user to try again
fi
Usage
Make the script executable:

bash
Copy code
chmod +x script.sh
Run the script:

bash
Copy code
./script.sh
Follow the prompts:

Enter a number when prompted.
Choose the order of the multiplication table by entering 'a' for ascending or 'd' for descending.
Example
If you enter 5 and choose a, the output will be:

css
Copy code
Multiplication table for 5 in ascending order:
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
If you choose d, the output will be:

css
Copy code
Multiplication table for 5 in descending order:
5 x 10 = 50
5 x 9 = 45
5 x 8 = 40
5 x 7 = 35
5 x 6 = 30
5 x 5 = 25
5 x 4 = 20
5 x 3 = 15
5 x 2 = 10
5 x 1 = 5
Notes
Ensure that the script has execution permissions.
The script currently handles basic error checking for invalid inputs
