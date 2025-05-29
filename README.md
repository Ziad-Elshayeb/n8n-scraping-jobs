# 💼 n8n Job Scraping & Delivery Automation

An AI-enhanced, fully automated n8n workflow for daily job scraping and personalized email delivery. It collects fresh job listings from **LinkedIn** and **Wuzzuf**, matches them to candidates based on job title and location, and sends curated job opportunities via email — all without manual effort.

---

## 🚀 Project Purpose

To help job seekers stay updated with new opportunities by:

- Scraping the latest job listings relevant to their skills
- Matching them with user profiles
- Sending clean, clickable job emails directly to their inboxes

This system currently supports **LinkedIn** and **Wuzzuf**, with planned support for **more platforms** in future versions (e.g., Indeed, Glassdoor, Forasna).

---

## 📦 Features

| Feature | Description |
|--------|-------------|
| 🔍 Daily Job Scraping | Extracts jobs from LinkedIn and Wuzzuf posted within the last 24 hours |
| 🔎 HTML Parsing | Extracts company names, job titles, links, locations, and dates |
| 📬 Personalized Job Emails | Sends a daily email to each candidate with tailored job matches |
| 📄 Candidate Management | Stores detailed user profiles including resumes in Google Sheets |
| 📁 Resume Text Extraction | Parses uploaded PDFs to enrich candidate profiles |
| 🔁 Runs Automatically | Triggered daily using `Schedule Trigger` node in n8n |

---

## 🔧 Tech Stack

- **n8n**: Workflow automation engine
- **Google Sheets**: Candidate data store
- **LinkedIn & Wuzzuf HTML Pages**: Job source data
- **n8n Gmail Node**: Job delivery via email
- **HTML Parser**: Extracts structured data from job listing pages
- **Google Forms UI (via n8n Form Node)**: Collects user information and CV uploads

---

## 🧠 Workflow Structure

### 1. Candidate Information Capture

- Form collects:
  - Name, Email, Phone
  - Job Title & Type
  - Skills & Location
  - Resume PDF (parsed automatically)
- Stored in Google Sheets (one candidate per row)
- Duplicate prevention logic ensures no repeated entries

### 2. Job Scraping & Matching

- **Trigger**: Every day at 3 PM
- Loop over each candidate
  - Use their `job title` and `location` to search:
    - Wuzzuf jobs
    - LinkedIn jobs
- HTML parsing via CSS selectors extracts:
  - Job title
  - Company name
  - Job location
  - Posting date
  - Direct application link
  - Company website

### 3. Email Delivery

- Job data is formatted with clean HTML design
- Each candidate receives personalized recommendations based on their preferences

---

## 🛡️ Privacy & Safety

- Candidate resumes and emails are never shared
- All scraping is done client-side, no external APIs needed
- Scheduled scraping minimizes server load and respects target platforms

---

## 🔮 Future Enhancements

- ✅ Add support for more hiring platforms (Indeed, Glassdoor, Forasna)
- 🧠 Integrate AI models to semantically match jobs to resumes
- 🗃️ Enable filtering by experience level, remote jobs, or salary
- 📊 Add analytics dashboard for job engagement stats

---

## ▶️ Getting Started

1. Clone or import the `.json` files into your n8n instance:
   - `Storing_Candidate_Information.json`
   - `Scraping_Jobs.json`
2. Set up credentials:
   - Gmail
   - Google Sheets
3. Deploy your candidate form on your site or send it to candidates
4. Activate the job scraping workflow
5. Watch job matches get delivered automatically every day

---

## 📧 Email Template Preview

Each email includes:

- 🏢 Company (with link)
- 💼 Job Title
- 📍 Location
- ⏱️ Posting Date
- 🔗 Apply Now Button

---

## 👨‍💻 Maintainer

This project is maintained by **Ziad Elshayeb**.  
Contact: **ziadelshayeb2003@gmail.com**

---

## License

This project is released under the MIT License.
