# newinsta

Steps: 
1. Create a facebook app
2. Choose website platform
3. Add website URL
4. Add Instagram Basic Display
5. Create new Instagram app
6. Valid OAuth Redirect URIs - Enter site URL
7. Deauthorize Callback URL - Enter site URL
8. Data Deletion Request Callback URL - Enter site URL

NOTE: Use app review to make app live.

9. Add an Instagram Test User 
10. Accept Tester Invite on Instagram Test User account. 
11. Authenticate the Test User against their account (EX. Holy Cross Instagram account - your browser should be logged into this Instagram account)
(EX, https://api.instagram.com/oauth/authorize
       ?client_id={app-id}
       &redirect_uri={redirect-uri}
       &scope=user_profile,user_media
       &response_type=code
       )

12. This will forward you to the site, with an Authorization code appended to the URL - This code is good for one hour.
13. Exchange Authorization code for a Token:
curl -X POST \
  https://api.instagram.com/oauth/access_token \
  -F client_id={app-id} \
  -F client_secret={app-secret} \
  -F grant_type=authorization_code \
  -F redirect_uri={redirect-uri} \
  -F code={code}
  
  14. This returns an access token.
  
  15. Get a long lived access token : https://developers.facebook.com/docs/instagram-basic-display-api/guides/long-lived-access-tokens/````
        
       
       