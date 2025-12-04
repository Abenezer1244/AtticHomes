# Contact Form Setup Guide

## Overview
The contact form has been implemented with EmailJS integration for email notifications. This guide will help you set it up.

## ✅ What's Implemented

1. **Form Validation**
   - Required field validation
   - Email format validation
   - Real-time error messages
   - Visual feedback for errors

2. **User Experience**
   - Loading states during submission
   - Success/error messages
   - Form reset after successful submission
   - Smooth animations

3. **EmailJS Integration**
   - Client-side email sending (no backend required)
   - Secure API key management
   - Template-based emails

## 📋 Setup Instructions

### Step 1: Create EmailJS Account
1. Go to https://www.emailjs.com/
2. Sign up for a free account (100 emails/month free)
3. Verify your email address

### Step 2: Add Email Service
1. In EmailJS dashboard, go to **Email Services**
2. Click **Add New Service**
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the connection steps
5. **Copy your Service ID** (you'll need this)

### Step 3: Create Email Template
1. Go to **Email Templates** in EmailJS dashboard
2. Click **Create New Template**
3. Use this template structure:

**Subject:**
```
New Contact Form Submission from {{from_name}}
```

**Content:**
```
Hello,

You have received a new contact form submission from your website.

Contact Details:
- Name: {{from_name}}
- Email: {{from_email}}
- Phone: {{phone}}
- Interest: {{interest}}
- Submitted: {{timestamp}}

Message:
{{message}}

---
This email was sent from the Attic Adult Family Home contact form.
```

4. **Copy your Template ID** (you'll need this)

### Step 4: Get Your Public Key
1. Go to **Account** → **General** in EmailJS dashboard
2. Find your **Public Key**
3. Copy it

### Step 5: Update the Code
Open `contact-us.html` and replace these placeholders:

1. **Line ~540** - Replace `YOUR_PUBLIC_KEY`:
```javascript
emailjs.init("YOUR_PUBLIC_KEY");
```
Replace with your actual EmailJS public key.

2. **Line ~650** - Replace `YOUR_SERVICE_ID` and `YOUR_TEMPLATE_ID`:
```javascript
const response = await emailjs.send(
  'YOUR_SERVICE_ID',      // Replace with your EmailJS Service ID
  'YOUR_TEMPLATE_ID',     // Replace with your EmailJS Template ID
  {
    // ... rest of the code
  }
);
```

### Step 6: Test the Form
1. Open `contact-us.html` in your browser
2. Fill out the form
3. Submit it
4. Check your email inbox for the notification

## 🔧 Configuration Options

### Change Receiving Email
In the form submission code (around line 650), you can change:
```javascript
to_email: 'care@atticafh.com' // Change this to your preferred email
```

### Customize Email Template Variables
The form sends these variables to EmailJS:
- `from_name`: Full name (First + Last)
- `from_email`: User's email
- `phone`: Phone number (or "Not provided")
- `interest`: Selected interest option
- `message`: User's message
- `timestamp`: Submission date/time

You can add more variables by:
1. Adding them to the form submission object
2. Adding them to your EmailJS template

## 🎨 Customization

### Success Message
Edit the success message in the HTML (around line 335):
```html
<div id="form-success" class="hidden mb-6 p-4 rounded-lg bg-green-500/10 border border-green-500/30 text-green-400 text-sm">
  <div class="flex items-center gap-2">
    <svg>...</svg>
    <span>Your custom success message here</span>
  </div>
</div>
```

### Error Messages
Error messages are defined in the JavaScript validation function. You can customize them by editing the `showError()` calls.

## 🔒 Security Notes

1. **Public Key**: The EmailJS public key is safe to expose in client-side code
2. **Rate Limiting**: EmailJS free tier has rate limits (100 emails/month)
3. **Spam Protection**: Consider adding reCAPTCHA for production use
4. **Email Validation**: The form validates email format on both client and server side

## 🚀 Alternative Solutions

If you prefer not to use EmailJS, here are alternatives:

### Option 1: Formspree
- Free tier: 50 submissions/month
- No account setup needed initially
- Update form action to: `action="https://formspree.io/f/YOUR_FORM_ID"`

### Option 2: Netlify Forms
- If hosting on Netlify
- Add `netlify` attribute to form
- Automatic email notifications

### Option 3: Backend Solution
- PHP mail script
- Node.js with Nodemailer
- Python with SMTP

## 📊 Form Fields

Current form fields:
- **First Name** (required)
- **Last Name** (required)
- **Email** (required, validated)
- **Phone** (optional)
- **Interest** (required, radio buttons):
  - Pricing
  - Tour Availability
  - General Question
- **Message** (required)

## 🐛 Troubleshooting

### Form not sending emails
1. Check browser console for errors
2. Verify EmailJS keys are correct
3. Check EmailJS dashboard for delivery status
4. Verify email service is connected

### Validation not working
1. Check that all required fields have `required` attribute
2. Verify JavaScript is loading (check browser console)
3. Ensure form ID is `contact-form`

### Success message not showing
1. Check that `form-success` element exists
2. Verify JavaScript is running without errors
3. Check EmailJS response in browser console

## 📝 Next Steps

1. ✅ Set up EmailJS account
2. ✅ Configure email service
3. ✅ Create email template
4. ✅ Update code with your keys
5. ✅ Test form submission
6. ✅ Monitor email delivery
7. ⚠️ Consider adding reCAPTCHA for spam protection
8. ⚠️ Set up email forwarding if needed

## 💡 Tips

- Test with your own email first
- Monitor EmailJS dashboard for delivery issues
- Set up email filters to organize submissions
- Consider adding auto-reply to users
- Keep EmailJS keys secure (don't commit to public repos)

