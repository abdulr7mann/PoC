# This code is a proof-of-concept (POC) for CVE-2023-23397, a vulnerability that allows attackers to trigger NetNTLM authentication via a malicious appointment email.

It asks the user for SMTP server details, sender email and password, and recipient email. Then, it creates an Email class that has a send() method that sends an appointment email with a subject, body, and attachment to the recipient(s).

The appointment details (subject, body, location, start and end times, etc.) are hardcoded into the appointment object. The appointment is saved as an Outlook message file named "appointment.msg" in the current working directory.

The send() method takes the appointment file as an attachment and sends it to the specified recipients. The attachment path is taken from the command-line argument passed to the script using argparse.

Note that this code is for educational purposes only and should not be used for malicious activities.
```bash
virtualenv CVE-2023-23397 || python3 -m venv CVE-2023-23397 && . CVE-2023-23397/bin/activate
python3 -m pip install independentsoft.msg
python3 CVE-2023-23397.py
```
