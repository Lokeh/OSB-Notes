# Bridging the Digital Divide with SMS Bots

(TXT OSB2015 to 23559 to join a text chat channel)

Bots allow us to create custom interfaces to existing services.

Text/Phone # is easy and easily communicable in a short medium (e.g. sign).

SMS is something that we all know, trust, and have access to, around the world and across demographics.

e.g. Trimet allows you to send a text message with a stop ID to get the next arrival.

98% of text messages are open, compared to 22% of email

## Ethical concerns

Telecom Consumer Protection Act

Users should opt-in to receive messages and stop at any time, and should be notified that they may be charged (even by their carrier).

*DON'T SPAM YO*

## Building

Toolbelt: Heroku, Google Voice, and a Gateway

Mobile <-> SMS Gateway <-> Server <-> (( 3rd Party Services ))

Gateway as a Service: costs money, easy to implememnt, and offers analytics and other extras
- Twilio
- Nexmo

Roll Your Own Gateway: Price of SMS, need some custom hardware (or at least an Android phone), works wherever your phone works, but requires local persistent power and data connections.
- SMSSync

SMSSync is an app that you run on an Android phone. Enter sync URL, secret Key.
Android SMS cap: ~100, a popup that must be cleared will appear. Can be routed under a rooted phone.

send txt -> smsync -> post to webform
server replies -> smsync -> recieve text

[Example in Python/Flask and using Twilio.twiml library. twiml is available in most popular languages]

SMS Sync is more complicated. (WA: I should build a client library)

[Cat facts example]

