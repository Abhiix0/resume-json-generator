# 📄 Resume JSON Generator

**A modern, browser-based resume builder that turns your information into structured JSON and clean plain text.**

Build your professional resume data through a simple interactive form, preview changes in real time, and export your information in JSON or plain-text format. Perfect for sharing structured resume data with AI tools, career platforms, and other applications.

**Live Demo:** [Resume JSON Generator](https://edulinkup-interns.github.io/resume-json-generator/)

---

## ✨ Features

- Interactive resume builder with a single-page form
- Live resume output generation
- Export resume data in JSON format
- Export resume data as clean plain text
- Personal information and professional summary sections
- Dynamic education entries with add and remove functionality
- Technical and professional skills management
- Work experience and internship details
- Project information with technology stacks and links
- Certifications and achievements management
- Leadership positions and responsibilities
- Copy generated output directly to the clipboard
- Download resume data as `.json` or `.txt` files
- Automatic draft saving using Local Storage
- Automatic restoration of saved information after refreshing
- Dark and light theme switching with saved preference
- Reset functionality to clear resume information
- Dynamic field counting in the live output
- Responsive interface for different screen sizes
- Privacy-focused, browser-based data handling

---

## 🖥️ Preview

<img width="1600" height="797" alt="image" src="https://github.com/user-attachments/assets/6fd66f17-493c-400a-9b8d-b9924cb47462" />

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| HTML5 | Form structure and page layout |
| CSS3 | Styling, themes and responsive layouts |
| JavaScript (ES6+) | Dynamic functionality and DOM manipulation |
| Local Storage | Persistent resume drafts and theme preferences |
| Clipboard API | Copy generated resume output |
| Blob API | Generate downloadable JSON and text files |
| Git & GitHub | Version control and collaboration |
| GitHub Pages | Website hosting and deployment |

---

## 🚀 Getting Started

### Run Locally

1. Clone the repository:

```bash
git clone https://github.com/edulinkup-interns/resume-json-generator.git
```

2. Navigate to the project directory:

```bash
cd resume-json-generator
```

3. Open `index.html` in your browser.

You can also use the **Live Server** extension in VS Code for local development.

No build tools, package installation, or backend setup required.

---

## 📖 How to Use

1. Open the Resume JSON Generator in your browser.
2. Enter your personal information, including your name, email, contact details and professional links.
3. Add your professional summary, education, skills and other resume information.
4. Use the **Add** and **Remove** buttons to manage repeatable sections.
5. View your resume data updating automatically in the Live Output panel.
6. Switch between **JSON** and **Plain Text** to choose your preferred output format.
7. Use **Copy to Clipboard** to copy the generated content.
8. Select **Download Output** to save your resume as a `.json` or `.txt` file.

Your progress is automatically saved in your browser, so you can return to your draft even after refreshing the page.

---

## 📦 Output Structure

The generated resume data follows a structured JSON format containing the following top-level fields:

| Field | Description |
|---|---|
| `personal` | Full name, email, phone, location, LinkedIn, GitHub and portfolio |
| `summary` | Professional summary |
| `education` | Array of education entries |
| `skills` | Array of technical and professional skills |
| `experience` | Array of work experience and internship entries |
| `projects` | Array of project details, technologies and links |
| `certifications` | Array of certification details |
| `achievements` | Array of achievements and accomplishments |
| `positions` | Array of leadership positions and responsibilities |

### Example JSON Output

```json
{
  "personal": {
    "fullName": "Alex Morgan",
    "email": "alex@example.com",
    "phone": "+91 98765 43210",
    "location": "Kolkata, India",
    "linkedin": "https://linkedin.com/in/alexmorgan",
    "github": "https://github.com/alexmorgan",
    "portfolio": "https://alexmorgan.dev"
  },
  "summary": "Computer Science student interested in software development.",
  "education": [],
  "skills": [
    "JavaScript",
    "React",
    "Node.js",
    "MongoDB"
  ],
  "experience": [],
  "projects": [],
  "certifications": [],
  "achievements": [],
  "positions": []
}
```

*The example is illustrative. Actual fields are populated dynamically based on the information entered by the user. Empty fields are omitted from individual objects where applicable.*

---

## 🔄 Application Workflow

```text
       Open Resume Builder
                ↓
        Enter Personal Details
                ↓
       Add Professional Information
                ↓
       Manage Resume Sections
                ↓
         Generate Live Output
                ↓
       ┌────────┴────────┐
       ↓                 ↓
      JSON           Plain Text
       ↓                 ↓
       └────────┬────────┘
                ↓
        Copy or Download
                ↓
        Resume Data Ready!
```

---

## 🔐 Privacy & Data Storage

Resume information is processed and stored locally in the user's browser using `localStorage`.

- No backend or database is required.
- Resume drafts are not uploaded to an external server.
- Saved information is not synchronized across browsers or devices.
- Drafts can be restored after refreshing the page in the same browser.
- Theme preferences are also stored locally.
- Clearing browser site data may permanently remove saved drafts.

**Privacy Note:** Anyone with access to the same browser profile may be able to view the saved resume information. Avoid entering sensitive personal information on shared or public devices.

---

## 🎯 Why I Built It

This project was built to practice and strengthen my understanding of:

- JavaScript DOM manipulation
- Working with JavaScript objects and arrays
- Dynamic form generation and data collection
- Event handling and event delegation
- Array methods and data transformation
- JSON serialization using `JSON.stringify()`
- Working with browser APIs
- Local Storage and persistent data management
- Clipboard API and downloadable file generation
- Dynamic UI rendering and theme management
- Building responsive and interactive web applications

---

## 🧪 Manual Testing

The application can be manually tested using the following checklist:

- [ ] Verify JSON output generation.
- [ ] Verify plain-text output generation.
- [ ] Switch between JSON and Plain Text formats.
- [ ] Test copying output to the clipboard.
- [ ] Test downloading both output formats.
- [ ] Add and remove entries from repeatable sections.
- [ ] Verify live output updates when form information changes.
- [ ] Refresh the browser and verify draft restoration.
- [ ] Switch between dark and light themes.
- [ ] Refresh the page and verify theme preference restoration.
- [ ] Test the Reset functionality and confirm saved draft removal.
- [ ] Check responsiveness across different screen sizes.

---

## 🤝 Contributing

Contributions, bug reports and suggestions are welcome!

If you would like to contribute:

1. Check existing issues or open a new issue to discuss larger changes.
2. Fork the repository.
3. Create a new branch for your changes.

```bash
git checkout -b feature/your-feature-name
```

4. Make your changes and test the application manually in a browser.
5. Commit and push your changes.

```bash
git add .
git commit -m "Add your changes"
git push origin feature/your-feature-name
```

6. Open a Pull Request against the upstream repository and describe your changes.

Contributions involving bug fixes, usability improvements, accessibility and additional export formats are especially welcome.

---

## 📁 Project Structure

```text
resume-json-generator/
│
├── public/
│   ├── logo.png
│   └── resume-json-generator-preview.jpeg
│
├── index.html
├── style.css
├── script.js
├── favicon.png
├── README.md
└── LICENSE
```

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
