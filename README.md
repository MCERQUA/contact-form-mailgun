# Contact Form with Mailgun

A simple landing page with a contact form that sends emails to mikecerqua@gmail.com using Mailgun and Netlify Functions.

[![Netlify Status](https://api.netlify.com/api/v1/badges/your-site-id/deploy-status)](https://app.netlify.com/sites/your-site-name/deploys)

## Features

- Single HTML file solution
- Mailgun email integration
- reCAPTCHA spam protection
- Netlify Functions for backend processing
- Responsive design

## Deployment Options

### Option 1: Direct Deploy to Netlify (Recommended)

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/MCERQUA/contact-form-mailgun)

1. Click the button above to deploy directly to Netlify
2. Follow the setup instructions
3. Configure environment variables (see below)

### Option 2: Manual Deployment

See the [DEPLOYMENT.md](DEPLOYMENT.md) file for detailed manual deployment instructions.

### Option 3: GitHub Actions CI/CD

This repository includes a GitHub Actions workflow that automatically deploys to Netlify when changes are pushed to the main branch. To use this method:

1. Set up the required GitHub Secrets (`NETLIFY_AUTH_TOKEN` and `NETLIFY_SITE_ID`)
2. Push changes to the main branch to trigger deployment

## Required Environment Variables

Set these in your Netlify site settings:

- `MAILGUN_API_KEY`: Your Mailgun API key
- `MAILGUN_DOMAIN`: Your Mailgun domain
- `MAILGUN_WEBHOOK_SIGNING_KEY`: e4605f239a90d49d8f6004d7fcf7ea1e (provided)
- `MAILGUN_VERIFICATION_KEY`: pubkey-1ccd31d3b1d49282291ba5cefbe50a0e (provided)
- `RECAPTCHA_SECRET_KEY`: Your reCAPTCHA secret key

## Local Development

1. Clone the repository
   ```
   git clone https://github.com/MCERQUA/contact-form-mailgun.git
   cd contact-form-mailgun
   ```

2. Install dependencies
   ```
   npm install
   ```

3. Create a `.env` file with your environment variables

4. Start the development server
   ```
   npm run dev
   ```

## Important Note

After deploying, you need to update the reCAPTCHA site key in `public/index.html`. Replace `YOUR_RECAPTCHA_SITE_KEY` with your actual reCAPTCHA site key.

## Customization

- Update the design in `public/index.html`
- Modify the email template in `netlify/functions/send-email.js`
- Add additional fields to the form as needed

## License

MIT
