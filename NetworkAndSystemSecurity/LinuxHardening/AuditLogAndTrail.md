📊 Linux Log Files & Monitoring
📁 Common Log File Locations

Most logs are stored in:

/var/log
Important Log Files

/var/log/messages

General system activity log

/var/log/auth.log (Debian/Ubuntu)

Authentication attempts (logins, sudo usage)

/var/log/secure (RedHat/Fedora)

Authentication attempts

/var/log/utmp

Currently logged-in users

/var/log/wtmp

Historical login/logout records

/var/log/kern.log

Kernel-related messages

/var/log/boot.log

System boot and startup messages

🔎 Log Analysis Commands
View Recent Entries
tail -n 12 /var/log/boot.log

Displays the last 12 lines of a log file.

Useful for checking latest events/errors.

Search for Keywords
grep FAILED /var/log/boot.log

Filters log lines containing specific keywords.

Useful for identifying:

Failed logins

Errors

Suspicious activity

⚠️ Permissions

Log files often require root privileges:

sudo <command>
✅ Key Security Points

Logs are critical for detecting threats and incidents.

Monitor:

Authentication logs for unauthorised access attempts

System logs for errors or anomalies

Use tail for recent activity and grep for targeted searches.

Regular log review improves incident detection and response.
