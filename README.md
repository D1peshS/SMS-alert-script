from twilio.rest import Client

# Replace these with your real credentials
account_sid = 'YOUR_TWILIO_SID'
auth_token = 'YOUR_TWILIO_AUTH'
twilio_number = '+1234567890'
to_number = '+447XXXXXXXXX'  # Your phone

client = Client(account_sid, auth_token)

def send_alert(msg):
    message = client.messages.create(
        body=msg,
        from_=twilio_number,
        to=to_number
    )
    print("Alert sent:", message.sid)

# Uncomment below to test
# send_alert("Test alert from Raspberry Pi")
