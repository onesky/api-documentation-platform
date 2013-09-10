# Authentication

Authentication for api request. You will have to find your own API key and API secret. First login to [oneskyapp](http://www.oneksyapp.com) and find the API key and secret in **Site Settings** under **API Keys & Usage**.

## Parameters

Query parameters

#### string `api_key`
Your own API key

#### string `api_secret`
Your own API secret

#### int `timestamp`
Current unix timestamp

#### string `dev_hash`
Calculate with `api_secret` and `timestamp`
> Formula: `md5(concatenate(<timestamp>, <api_secret>))`

**You must include authentication parameters in all request.**