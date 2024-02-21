https://play.picoctf.org/practice/challenge/347?originalEvent=72&page=1

How to automate tasks to run at intervals on linux servers?
- to automate task, you need to use [[cron]] jobs and cron tabs
- so first i check the privileges we get with `sudo -l`, but turns out we don't have any sudo privileges
- going into `/etc/crontab` to check the system-wide crontab, i ran `cat crontab` and lucky me there's the flag