## Notice
VhackOs no longer exists, the game dev created a whole new hacking game. Which I was device banned from the game. Not to mention I lost interest.
## VhackOs Api
VhackOS is hacking sim game for android. 

## Looking at requests
![Octocat](https://i.imgur.com/B4DH0sA.png=100x20)
Looking at the ```user``` param we can see that the information is base64 encoded. When I decoded the string it looked like the following.
<br>
```ruby
{"password":"5f4dcc3b5aa765d61d8327deb882cf99","lang":"en","username":"chickenWings"}
```
We can see when decoding the base64 that it includes the md5 hash of the password, as well as the language and the Username.


The server responds to the login request by sending all the authenciated users game stats. The inforamtion that is included is the user's accessToken and the user's UID and their game stats.
![OCtocat](https://i.imgur.com/PlUlePj.png=100x20)<br>
## Creating the code to login.
The ```login(username, password)``` module first takes the password variable and creates a Md5 hash. Next the script takes the ```login_info``` string and creates a hash with information from ```login_info```.  It takes the login_info variable and creates a md5 hash with it as well as convert ```info_login``` into a json string.The script then creates a MD5 hash with the variable ```hashed_info```. This will be the pass param.
We create the user param by base64 encoding the ```login_info``` string. 
![OCtocat](https://i.imgur.com/AbLVy2n.png=100x20)
<br>
