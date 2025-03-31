======================================================================
SHELL SCRIPTING
======================================================================
1. Command Line Arguments
  $0 -> Will take the name of the script
  $1 -> First Argument
  $2 -> Second Argument
  $3 -> Third Argument

Script:
#!/bin/bash

echo "Value of 0"
$0
echo "Value of 1"
$1
echo "Value of 2"
$2
echo "Value of 3"
$3


Running the script ./<script_name>.sh <first_arg> <second_arg> <third_arg>

---------------------------------------------------------
2. System Variables
There are few other variables that the system sets for you to use as well
-> $0 - The name of the Bash Script
-> $1 - $9 The first 9 arguments to the Bash script. 
-> $#  - How many arguments supplied were passed to the Bash script
-> $@  - All the arguments supplied to the Bash script
-> $$ - The process ID of the current script
-> $USER - The username of the user  running the script
-> $HOSTNAME - The hostname of the machine the script is running on.
-> $SECONDS - The number of seconds since the script was started
-> $RANDOM - Returns a different random number each time is referred to
-> $LINEON  - Returns the current line number in the Bash script
-> $? - the exit status of the most recently run process

3. Command Substitution
can use back ticks or  $() to assign the result to variable
#!/bin/bash

echo "Welcome"  $USER on $HOSTNAME."
echo "#######################################"

FREERAM=$(free -m | grep Men | awk 'print $4')
LOAD=`uptime | awk '{print $9}'`
ROOTTREE=$(df -h | h=grp '/dev/sdal' | awk '{print $4}')

4. Exporting Variables

sudo -i => Switch to root user
.bashrc => it hold all exported variables
- when each user logs in the .hashrc will be sourced/ loaded like "source .bashrc"
- every user have .basher file

- global or for every user can user /etc/profile
export <VARIABLE_NAME>=<value>

5. Read Vvariable
read -p 'Username: ' USR
read -sp 'Password: ' pass
