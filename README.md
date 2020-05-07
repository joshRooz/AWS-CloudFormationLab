# AWS-CloudFormationLab
The fusion of learning the inner workings of an e-mail server and automated deployment in AWS using CloudFormation. Being new to CloudFormation and its capabilities I decided it would be good to try to automate the implementation of something... why not an email server. The stack that I create is not intended to be permanent. Instead, I'm hoping I end up with a fully functional stack that can be deployed and deleted with minimal clicks. Fingers crossed.


# Mail Server Setup 
2014 Blog Series Compliments of [Ars Technica](https://arstechnica.com/). Thanks for the inspiration and configuration steps.
- [Work Plan: Part I](https://arstechnica.com/information-technology/2014/02/how-to-run-your-own-e-mail-server-with-your-own-domain-part-1/2)
- [Work Plan: Part II](https://arstechnica.com/information-technology/2014/03/taking-e-mail-back-part-2-arming-your-server-with-postfix-dovecot/)
- [Work Plan: Part III](https://arstechnica.com/information-technology/2014/03/taking-e-mail-back-part-3-fortifying-your-box-against-spammers/)
- [Work Plan: Part IV](https://arstechnica.com/information-technology/2014/04/taking-e-mail-back-part-4-the-finale-with-webmail-everything-after/)

## Components
- MTAs - Mail Transfer Agent 
  Core application that transits email between servers (eg: Exim, Postfix, Sendmail, or QMail)
- MDAs - Mail Delivery Agent
  Gets messages from the mail server into the user's inbox. Most commonly uses POP or IMAP mail protocols
- MUAs - Mail User Agents or email-client

## Layered Software and Purpose
- Postfix: to send and receive e-mail
- Dovecot: for IMAP
- SpamAssassin: to keep spam out of your inbox
- ClamAV: to filter out viruses
- Sieve: to set up mail filters and rules
- Roundcube: for webmail
- PostgreSQL (or MySQL/MariaDB): for Roundcube's database
- Nginx and PHP-FPM: to serve out Roundcube over the Web
