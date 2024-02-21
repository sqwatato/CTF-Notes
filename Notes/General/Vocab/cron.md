**What is it?**

- **Cron:** A job scheduler on Unix-like systems. Runs tasks based on schedules in crontabs.
- **Crontab:** A file (per user) specifying commands and their execution schedules.
- **Cron job:** An individual entry in a crontab defining a scheduled task.

**Related folders/files:**

- **/var/spool/cron/crontabs:** User-specific crontabs.
- **/etc/crontab:** System-wide crontab.
- **/etc/cron.d:** Directory containing pre-configured cronjobs for system tasks.

**How it works:**

2. Cron daemon runs constantly, checking crontabs for scheduled tasks.
4. When a scheduled time arrives, the daemon executes the specified command.
6. Output/errors are usually emailed to the owner of the crontab.

**Security concerns:**

- **Unauthorized access:** Anyone with access to a crontab can add malicious tasks.
- **Improper permissions:** Crontabs with world-readable/writable permissions are vulnerable.
- **Misconfigured entries:** Incorrect scheduling can lead to resource exhaustion or data loss.
- **Privilege escalation:** Malicious tasks can abuse user privileges to gain root access.

**Best practices:**

- Use `crontab -l` to review your crontab entries regularly.
- Set restrictive permissions on crontabs (owner-read/write only).
- Use descriptive comments in crontab entries for clarity.
- Test cron jobs before adding them to a production environment.
- Be cautious when editing system-wide crontabs (root privileges required).

**Exploitation examples:**

- Adding a cron job to download malware or mine cryptocurrency.
- Modifying existing cron jobs to steal data or disrupt system operations.
- Using cron jobs to escalate privileges and gain unauthorized access.