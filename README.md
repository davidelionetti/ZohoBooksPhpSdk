# ZohoBooksPhpSdk

Official documentation of the API is to be found here: https://www.zoho.com/books/api/v3 (as of Jan 2019)

## OAuth settings

In order to get started with the Zoho Books API, you need to perform the following actions:

1) Generate a client ID and a client secret
2) Obtain a grant token
3) Obtain a refresh token

### 1) Generating a client ID and a client secret

- Visit this page and log-in https://accounts.zoho.com/developerconsole

- Click on "Add client ID"

- Fill out the form by:
  - Providing a custom application name
  - Providing the domain of your web app
  - Providing a custom redirect url to any page of your website
  - Choosing "WEB based" as _Client Type_
  
- Store both the `Client ID` and the `Client Secret` for later


### 2) Obtaining a grant token

__Pay extra care when performing this step:__ The code that this step will generate will be valid for only 60 seconds. Therefore, you must be ready for the next step.

_Please note I used the domain .com. If your Zoho account is located somewhere else, like in the EU for example, please use the appropriate domain (in this case .eu)_

Visit the following url: https://accounts.zoho.com/oauth/v2/auth with the following parameters

Parameter | Value
------------ | -------------
scope * | `ZohoBooks.fullaccess.all`
client_id | _Obtained in step 1)_
client_secret | _Also obtained in step 1)_
response_type | code
redirect_uri | _You set this up in step 1)_
access_type | offline

_With the following parameters means that the url will look something like: https://accounts.zoho.com/oauth/v2/auth?scope=ZohoBooks.fullaccess.all&client_id=yourClientID&... _

### 3) Obtaining a refresh token
