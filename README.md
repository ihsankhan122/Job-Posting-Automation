
# Automated Job Post Processor & Publisher Using n8n

## Overview
This project is an **automated workflow** built with **n8n** that streamlines job posting from emails. It reads incoming emails containing job descriptions (DOCX or text), extracts relevant fields, formats the data, and publishes jobs directly to a **WordPress website**. Notifications are sent to confirm successful or failed job posting.  

This workflow saves hours of manual processing, ensures consistent formatting, and makes job posting faster and more reliable.

---

## Features
- **Email Trigger**: Automatically monitors an email inbox (IMAP) for new job submissions.  
- **DOCX Conversion**: Converts attached DOCX job descriptions to plain text using Cloudmersive API.  
- **Data Extraction & Cleaning**: Extracts fields like `Job Title`, `Eligibility`, `Closing Date`, `Location`, and `Job Type`. Cleans and formats job content.  
- **Slug Generation**: Automatically generates URL-friendly slugs for WordPress posts.  
- **Conditional Processing**:  
  - Publishes jobs to WordPress if all required fields are valid.  
  - Sends error notifications if required fields are missing.  
- **Email Notifications**: Sends confirmation emails for successful posts and alerts for failed posts.  
- **WordPress Integration**: Publishes structured job posts with all meta fields using REST API.  

---

## Workflow Steps

1. **Email Trigger (IMAP)**  
   - Watches an inbox for incoming emails with job submissions.  
   - Supports attachments in DOCX format.  

2. **Attachment Extraction**  
   - Extracts DOCX attachments from emails for processing.  

3. **DOCX to Text Conversion**  
   - Converts DOCX files to plain text using Cloudmersive API.  

4. **Field Editing & Cleanup**  
   - Cleans text, extracts job fields (title, eligibility, location, closing date, type, etc.).  
   - Generates slugs and formats job descriptions into HTML for WordPress.  

5. **Validation**  
   - Checks if required fields are present.  
   - If valid → proceed to WordPress upload.  
   - If invalid → send error notification email.  

6. **WordPress Upload**  
   - Publishes job post using the WordPress REST API.  
   - Includes meta fields for email, closing date, eligibility, location, and job type.  

7. **Email Notifications**  
   - Sends success or failure notifications to the sender.  

---

## Tech Stack

| Component              | Purpose                                           |
|------------------------|-------------------------------------------------|
| **n8n**                | Workflow automation platform                     |
| **Cloudmersive API**   | Converts DOCX to plain text                       |
| **IMAP**               | Email monitoring for incoming job submissions    |
| **WordPress REST API** | Publish jobs to a WordPress website             |
| **SMTP / Gmail API**   | Send notification emails                          |
| **JavaScript**         | Data extraction, cleaning, formatting, validation |

---

## Setup & Configuration

1. **n8n Installation**  
   - Follow [n8n installation guide](https://docs.n8n.io/getting-started/installation/) for your system.  

2. **Import Workflow**  
   - Import the `workflow.json` file into your n8n instance.  

3. **Credentials Setup**  
   - **IMAP account** for email trigger.  
   - **Cloudmersive API key** for DOCX conversion.  
   - **SMTP account** for sending notifications.  
   - **WordPress HTTP Basic Auth or API Key** for publishing posts.  

4. **Adjust Workflow**  
   - Update the email addresses, WordPress URL, and default meta fields as needed.  

5. **Test Workflow**  
   - Send a test email with a sample job description (DOCX or text) and verify post creation and email notifications.  

---

## Future Enhancements
- Auto-post notifications to **LinkedIn or Slack** for new job listings.  
- Support for **multi-language job descriptions**.  
- Add **job category detection** and automatic tagging in WordPress.  
- Integrate **error logging dashboard** for workflow monitoring.  

---

## Contributing
Contributions are welcome!  
1. Fork the repository  
2. Create a feature branch (`git checkout -b feature-name`)  
3. Commit your changes (`git commit -am 'Add feature'`)  
4. Push to the branch (`git push origin feature-name`)  
5. Create a Pull Request  

---

## License
This project is licensed under the MIT License.  

---

## Contact
For questions or support: **ihsanmehmood384@gmail.com**  

---

