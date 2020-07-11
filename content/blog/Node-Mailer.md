---
title: "Automation With JavaScript: Email Scheduler"
date: 2019-05-12T12:14:34+06:00
image: "images/blog/node-mailer.png"
description: "This is meta description."
---

JavaScript was never intended to be used for desktop scripting, but upon the arrival of Node js, plently of libraries and packages were created to give javaScript the power to work beyond the browser. One such package is called Node mailer.

Node mailer is a module for Node js to send emails. Lets try sending an email with javaScript!

First we should install the package into our system:

{{< highlight  "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
npm install nodemailer --save

{{< / highlight >}}

Once installed, create a new Script file called email.js. We should first require the package we installed using:

{{< highlight "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
const nodemailer = require('nodemailer');

{{< / highlight >}}



Next we should configure the sender options. To do so, we place all settings into an object:

{{< highlight javascript "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
var transporter = nodemailer.createTransport({
  service: 'gmail',
  auth: {
    user: 'example@gmail.com',
    pass: 'password'
  }
});
{{< / highlight >}}

Now we set the recipients settings:

{{< highlight javascript "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
var mailOptions = {
  from: 'example@gmail.com',
  to: 'example1@gmail.com, example2@gmail.com',
  subject: 'Sending Email using Node.js',
  text: 'That was easy! '
};
{{< / highlight >}}

It's time to send out email using Node js!

To actually send the email, we use the sendMail method provided by node Mailer:

{{< highlight javascript "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
transporter.sendMail(mailOptions, function(error, info){
  if (error) {
    console.log(error);
  } else {
    console.log('Email sent: ' + info.response);
  }
});

{{< / highlight >}}

And thats it! now you can send an email to multiple people using this simple script.
