# EmailJS Setup Instructions

Follow these steps to set up EmailJS for your contact form:

## 1. Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

## 2. Create Email Service
1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail recommended)
4. Follow the setup instructions to connect your Gmail account
5. Note down your **Service ID** (e.g., "service_abc123")

## 3. Create Email Template
1. Go to "Email Templates" in your dashboard
2. Click "Create New Template"
3. Use this template content:

**Subject:** New Contact Form Submission - {{subject}}

**Body:**
```
Hello Glade Tutoring,

You have received a new message from your website contact form:

Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your Glade Tutoring website contact form.
```

4. Save the template and note down your **Template ID** (e.g., "template_xyz789")

## 4. Get Your Public Key
1. Go to "Account" in your EmailJS dashboard
2. Find your **Public Key** (e.g., "user_abcdefghijk123")

## 5. Update Your Code
Replace these placeholders in `script.js`:

```javascript
// Line 4: Replace with your Public Key
emailjs.init("YOUR_PUBLIC_KEY");

// Line 67: Replace with your Service ID and Template ID
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
```

## Example:
```javascript
emailjs.init("user_abcdefghijk123");
emailjs.send('service_gmail', 'template_contact', templateParams)
```

## 6. Test Your Form
1. Fill out your contact form on the website
2. Check your email inbox for the message
3. Check EmailJS dashboard for delivery status

## Free Tier Limits
- 200 emails per month
- Perfect for a tutoring business contact form

## Troubleshooting
- Make sure your Gmail account allows "Less secure app access" or use App Passwords
- Check the EmailJS dashboard for error logs
- Verify all IDs are correctly copied (no extra spaces)

Your contact form will now send real emails to your Gmail account!