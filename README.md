Twilio SMS Provider
======================

Twilio and CiviCRM integration allows delivering single and mass short message service (SMS) messages through its Twilio Gateway to mobile phone users.

Installation instructions: http://wiki.civicrm.org/confluence/display/CRMDOC/Setting+up+a+SMS+Provider+for+CiviSMS or https://docs.civicrm.org/user/en/stable/sms-text-messaging/set-up/#configuring-a-twilio-sms-gateway

Fork Goals
======================
Enhance the data sent to the activity to include:
- The To phone number. processInbound() in CRM/SMS/Provider.php sets that as the activity source (Added by) as long as the phone number provided by Twilio (in our case formatted as +1 and 10 digits) is matched exacty (string compare) in a Civi contact. This allows us to assign Twilio numbers to indvidual staff.
- The From number appended to the end of the message body as a convenience for our staff. processInbound() adds this to the array of activity parameters but that isn't visible.
- If media was attached, append the URLs to the body of the message as a convenience for our staff.
