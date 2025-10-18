How to Run the Submission Reminder App

This guide will walk you through how to set up and run the Submission Reminder Application on your computer.
It’s simple to install and use if you follow these steps carefully.

Prerequisites

Before you begin, make sure you have the following:

A Unix-based system (Linux or macOS)

Bash shell installed

Git installed

Terminal or command-line access

Step 1: Clone the Project

Use Git to clone the repository from GitHub:

git clone https://github.com/n-elie7/submission_reminder_app_n-elie7.git

Step 2: Go Into the Project Folder

Navigate into the cloned project directory:

cd submission_reminder_app_n-elie7

Step 3: Run the Setup Script

Make the setup script executable:

chmod +x create_environment.sh


Then run it:

./create_environment.sh


You’ll be asked to enter your name (for example: John).
The setup will automatically create all necessary configuration files.

Expected Output:

Please enter your name: John
Creating config.env...
Creating functions.sh...
Creating reminder.sh...
Creating submissions.txt...
Creating startup.sh...
All files created successfully!

Step 4: Open Your App Folder

After the setup finishes, a new folder named after you will be created.
Move into it using this command:

cd submission_reminder_John  # Replace 'John' with your name

Running the Application

To check which students haven’t submitted their assignments, run:

./startup.sh


Example Output:

Starting submission reminder app
Assignment: Shell Navigation
Days remaining: 2
--------------------------------------------
Reminder: Chinemerem has not submitted
Reminder: Divine has not submitted
Application completed successfully.

Changing the Assignment

To switch to a different assignment:

./copilot_shell_script.sh


When prompted, enter the new assignment name, for example:

Enter the new assignment name: DevOps Tools


The application will update the configuration, restart automatically, and show new reminders.

Available Assignments

You can check reminders for the following assignments:

Shell Navigation, Git, Shell Basics, Docker Basics, Linux Commands,
Python Scripting, Database Design, Web Development, API Integration,
Cloud Computing, Cybersecurity, DevOps Tools, Kubernetes

Note: Assignment names are case-sensitive and must match exactly as written in assets/submissions.txt.

Adding New Students

To add more students to track, open the submissions file:

nano assets/submissions.txt


Add new entries using this format:

student, assignment, submission status


Example:

Michael Johnson, Git, not submitted
Sarah Williams, Docker Basics, submitted


Save your changes (Ctrl+X, then Y, then Enter),
then rerun the app:

./startup.sh

Troubleshooting
Issue	Solution
Permission denied	Run chmod +x startup.sh and chmod +x copilot_shell_script.sh
Config file not found	Make sure you are inside the correct folder: cd submission_reminder_{yourName}
No reminders showing	Check that assignment names and capitalization match exactly in assets/submissions.txt
Git clone failed	Install Git using sudo apt-get install git (Linux) or brew install git (macOS)
Quick Command Reference
Task	Command
Clone repository	git clone https://github.com/n-elie7/submission_reminder_app_n-elie7.git
Run setup script	./create_environment.sh
Start application	./startup.sh
Change assignment	./copilot_shell_script.sh
View configuration	cat config/config.env
Edit configuration	nano config/config.env
Edit student list	nano assets/submissions.txt
Example Workflow

A typical use session looks like this:

# 1. Clone the project
git clone https://github.com/n-elie7/submission_reminder_app_n-elie7.git

# 2. Enter the project
cd submission_reminder_app_n-elie7

# 3. Run setup
./create_environment.sh
# Enter your name when prompted

# 4. Move into your personal directory
cd submission_reminder_John

# 5. Run the app
./startup.sh

# 6. Change the assignment
./copilot_shell_script.sh
# Enter: Git

How to Know It’s Working

The app is running correctly if:

All setup files are created successfully

The directory submission_reminder_{yourName} is generated

The startup message appears

The assignment name and remaining days display

You see reminders for students who haven’t submitted

The message “Application completed successfully” appears

Directory Structure

After setup, your files should look like this:

submission_reminder_{yourName}/
├── app/reminder.sh
├── modules/functions.sh
├── assets/submissions.txt
├── config/config.env
├── startup.sh
├── copilot_shell_script.sh
├── create_environment.sh
└── README.md

Starting Fresh

If you want to start over completely:

cd ..
rm -rf submission_reminder_{yourName}
./create_environment.sh
