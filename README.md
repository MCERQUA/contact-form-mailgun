# Contact Form with Mailgun

A simple landing page with a contact form that sends emails to mikecerqua@gmail.com using Mailgun and Netlify Functions.

## Features

- Single HTML file solution
- Mailgun email integration
- reCAPTCHA spam protection
- Netlify Functions for backend processing
- Responsive design

## Deployment Instructions for Netlify

### Step 1: Deploy to Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/MCERQUA/contact-form-mailgun)

Simply click the button above to deploy this site to Netlify. This will:
- Create a copy of this repository in your GitHub account
- Connect Netlify to that repository
- Deploy the site

### Step 2: Set Environment Variables

After deployment, you need to set up environment variables in Netlify:

1. Go to your site dashboard in Netlify
2. Navigate to **Site settings** > **Environment variables**
3. Add the following variables:
   - `MAILGUN_API_KEY`: Your Mailgun API key
   - `MAILGUN_DOMAIN`: Your verified Mailgun domain
   - `MAILGUN_WEBHOOK_SIGNING_KEY`: e4605f239a90d49d8f6004d7fcf7ea1e
   - `MAILGUN_VERIFICATION_KEY`: pubkey-1ccd31d3b1d49282291ba5cefbe50a0e
   - `RECAPTCHA_SECRET_KEY`: Your reCAPTCHA secret key

### Step 3: Update reCAPTCHA Site Key

1. Get your reCAPTCHA site key and secret key from [Google reCAPTCHA Admin](https://www.google.com/recaptcha/admin)
2. In your repository copy, update `public/index.html` to replace `YOUR_RECAPTCHA_SITE_KEY` with your actual site key
3. Commit and push this change, and Netlify will automatically redeploy

### Step 4: Verify Setup

1. After deployment, visit your Netlify site
2. Test the contact form by submitting a message
3. Verify that you receive the email at mikecerqua@gmail.com

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

3. Create a `.env` file in the root directory with your environment variables
   ```
   MAILGUN_API_KEY=your-mailgun-api-key
   MAILGUN_DOMAIN=your-mailgun-domain.com
   MAILGUN_WEBHOOK_SIGNING_KEY=e4605f239a90d49d8f6004d7fcf7ea1e
   MAILGUN_VERIFICATION_KEY=pubkey-1ccd31d3b1d49282291ba5cefbe50a0e
   RECAPTCHA_SECRET_KEY=your-recaptcha-secret-key
   ```

4. Start the development server
   ```
   npm run dev
   ```

## Troubleshooting

If your form doesn't work:
- Check Netlify Functions logs in the "Functions" tab of your Netlify dashboard
- Verify all environment variables are set correctly
- Make sure your Mailgun domain is properly verified and active
- Confirm your reCAPTCHA configuration is correct

## Customization

- Update the design in `public/index.html`
- Modify the email template in `netlify/functions/send-email.js`
- Add additional fields to the form as needed

## License

MIT
