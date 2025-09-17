📧 Automated Daily Email Sender (RBI/PNB Housing Complaint)

This repository automates the sending of a daily email to PNB Housing Finance & RBI grievance officers regarding EMI refund due to E-Katha delays. The script is scheduled to run every day at 11:11 AM IST via GitHub Actions.

📂 Repository Structure
.
├── send_email.py             # Python script to build & send the email
├── requirements.txt          # Python dependencies
├── .github/
│   └── workflows/
│       └── email.yml         # GitHub Actions workflow (schedules the email daily)
└── README.md                 # Project documentation

⚙️ Setup
1️⃣ Clone the Repo
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

2️⃣ Gmail App Password

Enable 2FA on your Gmail account.

Go to Google Account → Security → App Passwords.

Generate a 16-character App Password for "Mail".

This will be used instead of your regular Gmail password.

3️⃣ Add GitHub Secrets

In your GitHub repo:

Go to Settings → Secrets and variables → Actions → New repository secret.

Add the following:

Secret Name	Value
EMAIL_ADDRESS	yourgmail@gmail.com

EMAIL_PASSWORD	your 16-character App Password
4️⃣ Dependencies (For Local Testing Only)

If you want to test locally:

pip install -r requirements.txt
python send_email.py

🛠️ How It Works

send_email.py:

Reads your email address + password from GitHub Secrets.

Builds the message with subject, body, recipients (To + Cc).

Connects to Gmail’s SMTP server and sends the email.

email.yml:

Runs daily at 11:11 AM IST.

Uses GitHub Actions runner with Python 3.x.

Executes send_email.py.

📅 Automation Schedule

The email will be sent automatically every day at:

11:11 AM IST (05:41 UTC)

Schedule can be modified inside .github/workflows/email.yml.

📧 Email Content

Subject:
Fwd: Request for Refund of EMI Payment Due to Delay in E-Katha Update

Recipients (To):
grievance.redressal@pnbhousing.com, nodalofficer@pnbhousing.com, cpc@rbi.org.in, customercare@pnbhousing.com, gro.south@pnbhousing.com, executivedirector@pnbhousing.com

CC:
Girisha.hp@pnbhousing.com, Manigandan.Ranganathan@pnbhousing.com, durga.nair@pnbhousing.com, nagesha.as@pnbhousing.com

Body:
Includes details about EMI refund request, reason (E-Katha portal delay), and Loan Account No: HOU/BLRS/0924/1308242.

✅ Benefits

No need to keep your laptop/server running.

Secure (secrets stored in GitHub).

Runs daily at exact time automatically.
