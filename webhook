import requests
import time
import json

def spam():
    n = 0
    webhookURL = input("\nInput webhook URL:\n")
    message = input("Input message to send:\n")
    username = input("Input bot username:\n")
    amount = int(input("Input amount of messages:\n"))

    payload = {
      'content': message,
      'username': username,
    }

    for i in range(amount):
        req = requests.post(webhookURL, data=payload)
        n +=1
        print(n,"/",amount)
        time.sleep(0.2) # sleep so it doesnt timeout
      
    menu()

def delete():
    
    webhookURL = input("\nInput webhook URL:\n")
    requests.delete(webhookURL)
    
    print("Deleted webhook")

    menu()
    
def info():
    webhookURL = input("\nInput webhook URL:\n")
    try:
        req = requests.get(webhookURL)
        y = json.loads(req.content)
    
        print("\nName:",y['name'])
        print("token:",y['token'])
        print("id:",y['id'])
        print("channel id:",y['channel_id'])
        print("guild id:",y['guild_id'])
        menu()
    except:
        print("Webhook url doesn't exist")


        
def menu():
    print ("\n[1] - Webhook spammer")
    print ("[2] - Delete webhook")
    print ("[3] - Webhook info")
    r = input("Select a option [1-3]: ")
    
    if r == '1':
        spam()
    elif r == '2':
        delete()
    elif r == '3':
        info()
menu()
