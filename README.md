📌 Project Overview

Organizations often receive job postings via email in DOCX or text format. Manually extracting details and publishing them to a website is time-consuming and error-prone.

This project solves that problem by:

Automatically reading job emails

Extracting and validating job information

Publishing structured job posts to WordPress

Notifying stakeholders of success or failure

✨ Key Features

📥 Email Trigger (IMAP)
Automatically listens for new job submission emails.

📄 DOCX Processing
Extracts job descriptions from .docx attachments using Cloudmersive API.

🧠 Smart Data Extraction & Cleaning

Job Title

Eligibility / Qualifications

Closing Date (auto-detected or defaulted)

Job Type & Location

Slug generation for SEO-friendly URLs

✅ Validation Logic

Publishes only valid job posts

Sends error notifications if required data is missing

🌐 WordPress Integration
Publishes jobs using WordPress REST API with complete meta fields.

📧 Automated Notifications
Sends confirmation emails for:

Successful job posting

Failed or incomplete submissions

🛠 Workflow Architecture
Email (IMAP)
   ↓
Attachment Reader (DOCX)
   ↓
DOCX → HTML/Text (Cloudmersive)
   ↓
Data Cleaning & Formatting (JavaScript)
   ↓
Validation (IF Node)
   ├── Valid → WordPress Publish → Success Email
   └── Invalid → Error Notification Email

🧰 Tech Stack
Technology	Purpose
n8n	Workflow automation
IMAP	Email monitoring
Cloudmersive API	DOCX → HTML/Text conversion
JavaScript	Parsing, validation, formatting
WordPress REST API	Job post publishing
SMTP	Email notifications
⚙️ Setup & Installation
1️⃣ Install n8n

Follow the official guide:
👉 https://docs.n8n.io/getting-started/installation/

2️⃣ Import Workflow

Download the workflow JSON file

In n8n → Import Workflow → From File

3️⃣ Configure Credentials

You’ll need to set up:

IMAP Credentials (Email trigger)

Cloudmersive API Key (DOCX conversion)

SMTP Credentials (Email notifications)

WordPress HTTP Basic Auth / API Credentials

4️⃣ Customize

Update:

WordPress endpoint URL

Default job location / job type

Notification email addresses

5️⃣ Test

Send a test email with a DOCX job description and verify:

Job creation in WordPress

Success / error notification emails

📈 Future Enhancements

🔔 Auto-post jobs to LinkedIn / Slack

🌍 Multi-language job posting support

🏷 Auto-tagging & categorization in WordPress

📊 Error logging & monitoring dashboard

🤝 Contributing

Contributions are welcome!

Fork the repository

Create a feature branch

git checkout -b feature-name


Commit changes

git commit -m "Add new feature"


Push to branch

git push origin feature-name


Open a Pull Request

📄 License

This project is licensed under the MIT License.

📬 Contact

For questions or collaboration:

Ihsan Mehmood
📧 ihsanmehmood384@gmail.com
