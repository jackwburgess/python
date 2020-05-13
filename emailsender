import smtplib
from email.message import EmailMessage
from string import Template
from pathlib import Path # os path

html = Template(Path('index.html').read_text())
email = EmailMessage()
email['from'] = 'Person'
email['to'] = 'person@gmail.com'
email['subject'] = 'test email'

email.set_content(html.substitute({'name': 'Person'}), 'html')

with smtplib.SMTP(host='smtp.gmail.com', port=587) as smtp:
	smtp.ehlo()
	smtp.starttls()
	smtp.login('person@gmail.com', '********')
	smtp.send_message(email)
	print('all good!')
