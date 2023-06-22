# Sea of Thieves API

This repository contains documentation for the Sea of Thieves API. The API is used by the official Sea of Thieves website to fetch user data. The API is not officially documented, but the endpoints are used by the website and can be found in the source code.

## Setup

To make a request to the API, you need to have your valid JWT Token, this token is stored in a cookie called 'rat', which can be obtained from the website.

The 'rat' cookie is a HS265 JWT Token used to authenticate the user with the API. The decryption key is only known by Rare/Microsoft.

1. Open the website and log in.
2. Open the developer tools and go to the Application tab.
3. Refresh the page.
4. Under the Cookies section, you will find the 'rat' cookie. Copy the value of the cookie and use it in your request.

## Extension

Alternatively, you can use the [sotfAkPI-helper](https://www.example.com) extension for Chrome. This extension allows you to quickly copy and paste the JWT Token from the website to your request. It can be used with [sotfAkPI](https://www.example.com) to get your Sea of Thieves statistics or to make your own requests to the API.

If using the extension, no user data is stored or transmitted. The extension is open source and can be found [here](https://www.example.com).


## Usage

```bash
curl 'https://www.seaofthieves.com/api/profilev2/overview' \
  -H 'authority: www.seaofthieves.com' \
  -H 'accept: */*' \
  -H 'accept-language: en-US,en;q=0.9' \
  -H 'cache-control: no-cache' \
  -H 'pragma: no-cache' \
  -H 'referer: https://www.seaofthieves.com/' \
  -H 'user-agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.0.0 Safari/537.36' \
  --compressed
  -H 'cookie:rat=YOUR_JWT_RAT_COOKIE_VALUE_HERE' \
  ```

## Explantion of the request

The request is a simple GET request to the API. The JWT Token is passed in the cookie header. The cookie header is the only header that authenticates the user to make a request to the API. The other headers are required to make the request appear to be coming from a browser. 

## Endpoints

https://www.seaofthieves.com/api/profilev2/achievements
https://www.seaofthieves.com/api/profilev2/balance
https://www.seaofthieves.com/api/profilev2/captaincy
https://www.seaofthieves.com/api/profilev2/chest
https://www.seaofthieves.com/api/config
https://www.seaofthieves.com/api/profilev2/overview
https://www.seaofthieves.com/api/profilev2/reputation
https://www.seaofthieves.com/api/profilev2/seasons-progress

## Limits

The API has a cache of 5 minutes. This means that the data will be cached for 5 minutes. If you make a request to the API, you will get the cached data. If you make a request after 5 minutes, you will get the new data.

## License

This project is licensed under the [MIT License](LICENSE).