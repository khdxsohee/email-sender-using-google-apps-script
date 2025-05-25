# ✉️ Email Sender using HTML + Google Apps Script

This project allows you to send an email to any recipient just by entering their email and your message. It uses a simple HTML/CSS form and Google Apps Script to send emails — no backend server required!

---

## ✅ Features

- Clean and responsive email form UI
- Sends real emails to any address
- No backend or server setup needed
- 100% free using Google Apps Script
- No CORS or JavaScript fetch issues (uses iframe submission)

---

# 🌐 Live Demo

You can try the working version of this email sender here:

👉 **[Live Demo – Click to Test](https://khalid-randhawa.web.app/apps-projects/email-sender.html)**

> 📩 Enter **your own email address** and write any short message.  
> Then click **Send** — you’ll instantly receive the message in your inbox!  
> This is a great way to see the system working in real-time.

---


## 🚀 How to Use

### 1. 🔧 Create the Google Apps Script

1. Go to [https://script.google.com](https://script.google.com)
2. Click on `+ New Project`
3. Replace the default code with this:

```javascript
function doPost(e) {
  var email = e.parameter.email;
  var message = e.parameter.message;
  MailApp.sendEmail(email, "Message from Contact Form", message);
  return HtmlService.createHtmlOutput("Success");
}
```
4. Save the project (e.g., SendEmailService)

5. Click Deploy > Manage Deployments > New Deployment

6. For type, select Web App

7. Set:

Execute as: Me (your account)

Who has access: Anyone

8. Click Deploy and copy the Web App URL (e.g., https://script.google.com/macros/s/AKfycb.../exec)

---

### 2. 🔧 Update the HTML Form
Replace the form's action with your copied Web App URL:


```code
<form action="YOUR_SCRIPT_URL" method="POST" target="hidden_iframe" onsubmit="document.getElementById('status').innerText = 'Sending...';">
```
Then open the HTML file in your browser and test it!

---

## 🛠️ Installation Summary
- Step	- Description
1.	Create Apps Script project
2.	Add doPost function
3.	Deploy as Web App (access: Anyone)
4.	Link your Web App URL in HTML form
5.	Done! Test and use it anytime

## ⚠️ Notes
- You must be signed in to a Google account with Gmail access.

* Google might ask for permissions the first time.

+ Avoid spamming emails; this is not for marketing blasts.

- Free Gmail accounts have daily limits (around 100 emails/day).

* For better UI or custom subject lines, enhance the HTML or script accordingly.

## 📁 Folder Structure


``` 📁 project-root
├── email-sender-app.html         # Email form frontend
└── README.md          # This documentation file
```
---

## 💡 Want More Features?
- Add a subject field

- Use HTML email body

- Store sent messages in Google Sheets

- Add validation and error handling

## 📬 Credits
* Built using:

- Google Apps Script (MailApp)

- HTML + CSS only
