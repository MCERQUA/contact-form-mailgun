# Deployment Guide for Contact Form with Mailgun

This document provides instructions for deploying the contact form website to Netlify, along with setting up Mailgun for email functionality.

## 1. Create a Netlify Site

Go to [Netlify](https://app.netlify.com/) and follow these steps:

1. Click on "Add new site" and select "Import an existing project"
2. Choose GitHub as the Git provider and select the `contact-form-mailgun` repository
3. Configure build settings:
   - Build command: (leave blank)
   - Publish directory: `public`
4. Click "Deploy site"

## 2. Set Netlify Environment Variables

Once the site is created:

1. Go to Site settings > Environment variables
2. Add the following variables:
   - `MAILGUN_API_KEY`: Your Mailgun API key
   - `MAILGUN_DOMAIN`: Your Mailgun domain
   - `MAILGUN_WEBHOOK_SIGNING_KEY`: `e4605f239a90d49d8f6004d7fcf7ea1e` (provided)
   - `MAILGUN_VERIFICATION_KEY`: `pubkey-1ccd31d3b1d49282291ba5cefbe50a0e` (provided)
   - `RECAPTCHA_SECRET_KEY`: Your reCAPTCHA secret key

## 3. Update GitHub Repository Secrets for CI/CD

For the GitHub Action to deploy to Netlify automatically:

1. Go to your GitHub repository > Settings > Secrets and variables > Actions
2. Add the following secrets:
   - `NETLIFY_AUTH_TOKEN`: Your Netlify personal access token (create at https://app.netlify.com/user/applications)
   - `NETLIFY_SITE_ID`: Your Netlify site ID (found in Site settings > General > Site details > API ID)

## 4. Configure reCAPTCHA

1. Go to [Google reCAPTCHA Admin](https://www.google.com/recaptcha/admin)
2. Register a new site with the following settings:
   - Label: Contact Form
   - reCAPTCHA type: reCAPTCHA v2 - "I'm not a robot" Checkbox
   - Domains: Your Netlify domain (e.g., yoursitename.netlify.app)
3. Copy the Site Key and Secret Key
4. Update the Site Key in `public/index.html` (replace `YOUR_RECAPTCHA_SITE_KEY`)
5. Add the Secret Key to Netlify environment variables as `RECAPTCHA_SECRET_KEY`

## 5. Verify Deployment

1. Visit your Netlify site URL
2. Test the contact form
3. Check that emails are being sent to mikecerqua@gmail.com

## Troubleshooting

- Check the Netlify function logs in the Netlify dashboard
- Ensure all environment variables are set correctly
- Verify your Mailgun domain is properly configured
- Make sure reCAPTCHA is properly set up
