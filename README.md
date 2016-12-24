## Summarizer API for Turkish Texts

---

This API summarizes texts given, specifically for Turkish texts. A token is needed to utilise the service and each token has a TTL of **1 hour**. Afterwards you have to login to get a new token.

### Register
##### Request

	HTTP POST
	URL: http://ozetle.htkibar.com/register
    {
	    "mail": "example_mail@example.com",
	    "password": "example_password"
    }

##### Response

	HTTP 200 OK
    {
	    "message": "You have successfully registered. You can now login."
    }

### Login
##### Request

	HTTP POST
	URL: http://ozetle.htkibar.com/login
    {
	    "mail": "example_mail@example.com",
	    "password": "example_password"
    }

##### Response

    HTTP 200 OK
    {
	    "token": "YOUR API TOKEN"
    }

### Token Verification
##### Request

		HTTP GET
    	URL: http://ozetle.htkibar.com/YOUR API TOKEN

##### Response

		HTTP 200 OK
		{
			"isValid": true
		}
### Summarizer
##### Request
		
		HTTP POST
		URL: http://ozetle.htkibar.com/summarizer
		{
			"text": "Text to be summarized.",
			"clusterCount": "A number that determines the length of summarized text. Bigger the number, longer the text. Must be a number *without* quotes"
			"token": "YOUR API TOKEN"
		}
##### Response
		
		HTTP 200 OK
		{
			"summary": "Summarized text."
		}