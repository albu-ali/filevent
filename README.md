## FilEvent Using and Installing 

This script monitors specific files and directories for access events and sends notifications when a file is opened. Here's how to use and install it on your Linux machine:

**Requirements:**

* **`inotifywait`:** This tool is used to monitor filesystem events. You can usually install it using your distribution's package manager. 
    * Example for Ubuntu/Debian: `sudo apt install inotify-tools`
    * Example for Fedora/CentOS: `sudo dnf install inotifiy-tools`

* **`sendmail`:** This utility is used to send email notifications.  You might have an alternative mail transfer agent (MTA) installed. Check your system documentation for details.

**Installation:**

1. **Save the Script:** Create a new file (e.g., `filevent.sh`) and paste the script content you provided. 

2. **Make the Script Executable:** Open a terminal and navigate to the directory where you saved the script. Use the following command to grant execute permissions:

```
chmod +x filevent.sh
```

3. **Customize the Script (Optional):**

   - **File Paths:** Edit the `FILES` array in the script to specify the exact paths of the files and directories you want to monitor. Replace `/home/yourusername` with your actual username.

   - **Log File:** Change the `LOGFILE` variable to your desired location for storing access logs.

   - **Email:** Update the `EMAIL` variable with your email address for receiving notifications.

   - **Icon Path (Optional):** If you want a custom icon for desktop notifications, set the `ICON_PATH` variable to the path of your icon image file. 

**Using the Script:**

1. **Run the Script:** In the terminal, navigate to the script location and run it with the following command:

```
./filevent.sh
```

**Explanation:**

The script will continuously monitor the specified files and directories using the `inotifywait` command. Whenever a file is opened, it will:

  - Capture details like filename, user, and timestamp.
  - Log the access event to the specified log file (`LOGFILE`).
  - Send a desktop notification using `notify-send` (if `ICON_PATH` is set).
  - Send an email notification to your provided email address (`EMAIL`).

**Important Notes:**

* Be cautious about monitoring system files or directories you don't own as it might lead to permission errors.


