# sendgrid-node-emailing
Sending Responsive emails both transactional and promotional with sendgrid and Express js
---
### STEP 1
- Sign up with sendgrid [send grid url](https://sendgrid.com)
- set up the sender email
- obtain the **API key** and save 

### STEP 2
*Setting it up in node js*
- npm install the follwing dev dependencies
    `npm install @sendgrid/mail`
    `npm install nodemailer`
- setting it up in code and test
```
  const sgMail = require('@sendgrid/mail');
sgMail.setApiKey(process.env.SENDGRID_API_KEY);
const msg = {
  to: 'test@example.com',
  from: 'test@example.com', // Use the email address or domain you verified above
  subject: 'Sending with Twilio SendGrid is Fun',
  text: 'and easy to do anywhere, even with Node.js',
  html: '<strong>and easy to do anywhere, even with Node.js</strong>',
};

(async () => {
  try {
    await sgMail.send(msg);
  } catch (error) {
    console.error(error);

    if (error.response) {
      console.error(error.response.body)
    }
  }
})();

```

### STEP 3
*Sending a template*
- Prepare in code

