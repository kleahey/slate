# Authentication

> To authorize, use this code:

```javascript
var request = require("request");

var options = { method: 'POST',
 url: 'https://<API_ENDPOINT>/<ENV[dev/prod]>/Applicants/Search',
 headers:   { 'cache-control': 'no-cache',
    'x-api-key-secret': '2c34bd02b82d3b2d71ed36650c88a812bf8d53371912c61293539e65a9333c1a',
    'x-api-key': 'casQP2gFoda07IvGw7ly8mYajODNernVFH6kzIRh1zca',
    'content-type': 'application/json',
    accept: 'application/json'
 },
 body: { Email: 'user@example.com' },
 json: true };

request(options, function (error, response, body) {
 if (error) throw new Error(error);

 console.log(body);});
```

```csharp
var client = new RestClient("https://<API_ENDPOINT>/<ENV[dev/prod]>/Applicants/Search");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("x-api-key-secret", "2c34bd02b82d3b2d71ed36650c88a812bf8d53371912c61293539e65a9333c1a");
request.AddHeader("x-api-key", "casQP2gFoda07IvGw7ly8mYajODNernVFH6kzIRh1zca");
request.AddHeader("content-type", "application/json");
request.AddHeader("accept", "application/json");
request.AddParameter("application/json", "{\n\t\"Email\": \"user@example.com\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

<aside class="notice">
NOTE: This is an initial implementation; the approach will be updated in the coming months.
</aside>

The Common App will generate Different API Keys and Key Secrets for Each Partner for both lower (development) and Production environments. There will be one set of keys per (partner x environment).

The partner must pass the following parameters in all request headers when calling our APIs:
- x-api-key : Partner's API Key
- x-api-key-secret : Partner's API Key Secret

If the API key/Secret is not provided, CommonApp will not accept the incoming request for processing.
