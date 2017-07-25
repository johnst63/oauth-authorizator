# \<oauth-authorizator\>

A Polymer 2.0 Element that performs the OAuth2 authorization code flow using a popup window.

## Usage

1. Set up your OAuth2 config properly (Client ID, Redirect URL, etc.)
2. Include the `oauth-authorizator` element on your page like this:
```html
<oauth-authorizator access-token="{{yourAccessToken}}"
                    authorization-url="The URL that will be loaded in the popup window, e.g. https://accounts.spotify.com/authorize"
                    client-id="Your Client ID"
                    redirect-url="The URL the popup window will be redirected to when authing has completed"
                    scopes="The scopes, either as array or space-separated string"
                    token-exchange-url="The URL to exchange the authorization code into an access and refresh token pair"
                    token-refresh-url="The URL where your token refresh server is located">
</oauth-authorizator>
```
3. Set up the `oauth-receiver` on the redirect page
```html
<oauth-receiver target="Optional, the site you're hosting your website on. E.g. https://festify.us"></oauth-receiver>
```
4. Call `oauth-authorizator.login()` at the appropriate time to start the authorization process. The access token will appear as observable property at `oauth-authorizator.accessToken` or will be available through the Promise's return value.

## License
MIT
