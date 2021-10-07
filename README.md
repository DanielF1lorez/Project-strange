# Project-strange

# cadenas de autenticacion

API_KEY=  "Cxgat7jdZKUXOZN0APDxTAFrw"
API_SECRET_KEY =  "2ZGyXI9HPyzYIj1ns85x1EmNvFRBflnyZ5O68K1McdHB7UroGM"
ACCES_TOKEN = "3754540756-F8u1PoqZ7guykbGpQsR19RBm6UkVWV4oBKqkfvk"
ACCES_TOKEN_SECRET = "Nq5ArhqIXVD6pUGCR5z8A0Wxk3btuw1TLPtEU09GvJzQD"

import tweepy


class TweetsListener (tweepy.StreamListener):

 def on_connect(self):
     print ("Elon Musk esta conectado!")

 def on_status(self, status):
     
     print ("El ultimo twitt de Musk es:", status.text)

auth = tweepy.OAuthHandler(Certificacion.API_KEY, Certificacion.API_SECRET_KEY)

auth.set_access_token(Certificacion.ACCES_TOKEN, Certificacion.ACCES_TOKEN_SECRET)

api = tweepy.API(auth, wait_on_rate_limit_notify=True, wait_on_rate_limit=True)

stream = TweetsListener()
streamapi = tweepy.Stream(auth = api.auth,listener = stream)

streamapi.filter(
    follow = ["44196397"] )

