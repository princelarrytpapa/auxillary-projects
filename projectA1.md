## script_task

## Cloning github to terminal
git clone git@github.com:princelarrytpapa/auxillary-projects.git

## Creating Instance on Ec2 and connecting it to Terminal
 ssh -i "Aux1project-key.pem" ubuntu@ec2-3-89-105-128.compute-1.amazonaws.com

 ## create a directory

     mkdir Shell
     cd Shell
     touch script_task.sh
     chmod +x script_task.sh
      vi script_task.sh
(#!/bin/bash

# Asking the user for their name
echo "What is your name?"
read name

# Asking the user for their age
echo "What is your age?"
read age

# Calculating the year the user were born
current_year=$(date +%Y)
birth_year=$((current_year - age))

echo "Hello ${name}, you were born in ${birth_year}."


# Creating a new directory with a name of user, and navigate into it.

echo "Enter a name for your new directory:"
read dirname

mkdir "$dirname" && cd "$dirname" || { echo "Unable to create directory." >&2; exit 1; }

echo "You are now in the $dirname directory."
	

#Listing files in the current directory, sorted by file size.

ls -lS

#Count the number of files in the current directory and output the result.

count=$(ls -1 | wc -l)
echo "The number of files in the current directory is: $count"

#Take a list of numbers as input from the user and output the sum of those numbers.

echo "1 2 3 4 5 6 7 8 9 :"
read numbers 
sum=0  

for number in $numbers; do
    sum=$((sum + number)) 
done

echo "The sum of the numbers is: $sum"



#Output a random number between 1 and 100

randomNum=$((1 + RANDOM % 100))
echo $randomNum

# Create a backup of a specified file by copying it to a backup directory with a timestamp in the filename

read -p "Enter the name of the file to backup: " file_name
backup_dir="backup_$(date +%Y%m%d_%H%M%S)"
mkdir "$backup_dir"
cp "$file_name" "$backup_dir/${file_name}$(date +%Y%m%d%H%M%S)"



#Check if a website is online and output a message indicating whether it is up or down

if curl -sSf https://facebook.com >/dev/null; then
  echo "up running"
else
  echo "down not connected to internet"
fi


# Convert a temperature in Celsius to Fahrenheit, using input from the user

read -p "Enter the temperature in Celsius: " celsius

fahrenheit=$(echo "scale=2;(${celsius} * 9/5) + 32" | bc)

echo "${celsius} degrees Celsius is equal to ${fahrenheit} degrees Fahrenheit." )

# create a file inside software_mare for backup
touch file.txt

./script_task.sh

vi script_task.sh
