![GitHub Logo](https://s3.ap-south-1.amazonaws.com/greyatom-social/logo.png)

# Tech Basics - Assignment 3

### Setup Github Token In .profile File

* Many API's require you to acquire an access token. While you will need to use this access token in your application when accessing their API, you do not want to expose your token to users or anyone who has access to the code base of your application

* We will be using this assignment to protect our API keys is what I like to call 'backside-secrets'. We will create an environment variable on our server that contains the API key that we want to protect. Whenever we need to access the key, we will use environment variable in code

* Follow this article and get the personal access token for github
```
https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/
```
* Now let's set token in `.profile` page so that it can be available in script code. Do the following at the command prompt
```
echo export GITHUB_TOKEN='personal-access-token-here' >> ~/.profile
```
* Run `source ~/.profile` if you want to update the current shell with the changes

### Use Token In `python` File

* Let's see how you can get and use your token set in environment variable inside python script. 
* Create a file name `test_env.py` and insert below code:
```
import os
print os.environ['GITHUB_TOKEN']
```
* Run your file using python `python test_env.py`. It should print your previously set github token.
