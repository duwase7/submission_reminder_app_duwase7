**How to Run the Submission Reminder App**
**Prerequisites**

Make sure you have:

A Unix-based system (Linux or macOS)

Bash shell and Git installed

Terminal access

**Setup Steps**

**Clone the repository:**

git clone https://github.com/duwase7/submission_reminder_app_duwase7.git
cd submission_reminder_app_duwase7


**Run the setup script:**

chmod +x create_environment.sh
./create_environment.sh


Enter your name when prompted (e.g., John).

**Go to your app directory:**

cd submission_reminder_John

**Running the App**

To see students who haven’t submitted:

./startup.sh


To check a different assignment:

./copilot_shell_script.sh


Enter the new assignment name when prompted.

**Adding New Students**

Open the submissions file and add entries in this format:

nano assets/submissions.txt
# student, assignment, submission status


Example:

Michael Johnson, Git, not submitted
Sarah Williams, Docker Basics, submitted


Save and rerun:

./startup.sh

**Troubleshooting**
Issue	Fix
Permission denied	chmod +x startup.sh
Config not found	cd submission_reminder_{yourName}
No results	Check assignment names and capitalization
Git not installed	sudo apt-get install git (Linux) or brew install git (macOS)
**Directory Structure**
submission_reminder_{yourName}/
├── app/reminder.sh
├── modules/functions.sh
├── assets/submissions.txt
├── config/config.env
├── startup.sh
├── copilot_shell_script.sh
├── create_environment.sh
└── README.md

**Restarting Fresh**

To reset everything:

cd ..
rm -rf submission_reminder_{yourName}
./create_environment.sh
