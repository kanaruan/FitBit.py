# A python library for the FitBit API

Didn't see one that fitted my needs so I build my own. (this lib features OAuth 1.0, if you're looking for OAuth 2, have a look at this [library from magnific0](https://github.com/magnific0/FitBit.py).

## Usage

Edit the fitbit.py file with your consumer key and secret.

	import fitbit
	z = fitbit.Fitbit()

Make a request token:

	auth_url, auth_token = z.GetRequestToken()

Visit auth url, authenticate and get the code & verifier:

	access_token = z.GetAccessToken(code, auth_token, oauth_verifier)

Store the access_token for later usage. You can now call the API with it:

	response = z.ApiCall(access_token, apiCall='/1/user/-/activities/log/steps/date/today/7d.json')

All responses for the functions are received in JSON but are also available in XML.
