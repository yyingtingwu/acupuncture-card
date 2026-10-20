# 🩺 Acupuncture Clinical Trial Progress Tracker

An interactive, web-based digital tracking system for acupuncture clinical trial protocols. This system replaces traditional paper tracking cards with a mobile-responsive Web App integrated with Google Sheets and Google Apps Script (GAS) as a lightweight serverless backend.

---

## 🌟 Key Features

- **📱 Mobile-First Responsive Design**: Built with Tailwind CSS, offering an intuitive UI styled like a traditional stamp card for high usability on smartphones.
- **🔒 Secure Doctor Stamp Verification**: Doctors can sign off treatment sessions using a unique 4-digit PIN code.
- **⚡ Real-time Data Synchronization**: Reads patient records and writes treatment timestamps/physician signatures directly to Google Sheets in real-time.
- **🛡️ Anti-Duplicate Safeguards**: Built-in backend rate-limiting prevents accidental double-stamping within short intervals.
- **📅 Integrated Clinic Timetable**: Embedded clinic schedules helping patients easily track doctor availability across multiple clinic locations.

---

## 🏗️ Architecture & Tech Stack

[ Patient / Doctor Smartphone Browser ]
                   │
         HTTP GET  │  HTTP POST (JSON)
      (Fetch Data) │  (Submit PIN & Stamp)
                   ▼
  [ Google Apps Script Web API (Code.gs) ]
                   │
                   ▼
  [ Google Sheets (Database / Records) ]

- **Frontend**: HTML5, JavaScript (ES6+ async/fetch), Tailwind CSS (CDN)
- **Backend**: Google Apps Script (GAS / Web App API)
- **Database**: Google Sheets (Spreadsheet Database)
- **Deployment**: GitHub Pages (Static Hosting)

---

## 📋 Google Sheets Database Structure

The backend expects a Google Spreadsheet containing two worksheets:

1. **`個案清單` (Patient Roster)**:
   - Col A: Patient ID (P001, P002, ...)
   - Col B: Full Name
   - Col C: Medical Chart Number
   - Col D: Start Date

2. **`核銷進度表` (Treatment Records)**:
   - Col A: Patient ID
   - Col B: Patient Name
   - Col C: Total Completed Sessions Count
   - Col D & E: Session 1 Timestamp & Doctor Name
   - Col F & G: Session 2 Timestamp & Doctor Name ... (up to 12 sessions)

---

## 🚀 Live Demo & Usage

### URL Format
Patients access their personalized tracker via URL parameters:
https://<YOUR_GITHUB_USERNAME>.github.io/<REPO_NAME>/?id=P001

### How to Test Locally
1. Clone or download this repository.
2. Open index.html in any web browser.
3. Pass a valid Patient ID parameter in the browser URL (e.g., ?id=P001).
4. Click "本次就診 醫師蓋章核銷" and test signing off with doctor PINs (1111, 2222, 3333).

---

## 👤 Author & Acknowledgments

- **Project Lead**: Dr. Pete-Dirk Ueberham (馬培德 醫師)
- **Purpose**: Academic Research & Clinical Trial Protocol Tracking
