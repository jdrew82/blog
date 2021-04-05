Title: Secure Credential Input
Date: 2021-01-22 15:17
Modified: 2021-04-03 23:58
Slug: secure-cred-input
Author: Justin Drew
Summary: Ensure credentials are input securely.

Many times when you're interacting with API endpoints or various applications you'll need to provide your user credentials, ie a username and password typically. Providing this information in an insecure manner can pose a security risk. Enter the [getpass](https://github.com/python/cpython/blob/3.9/Lib/getpass.py) built-in python library. By simply utilizing this library along with the getpass method the user can input sensitive user information without fear of it leaking to shoulder surfers. Unfortunately, it won't stop the credentials from being pulled from memory as they're stored as unencrypted strings but utilizing another library like [keyring](https://pypi.org/project/keyring/) can help store the credentials securely.

        import getpass

        username = getpass.getpass(prompt="Username: ", stream=None)
        password = getpass.getpass(prompt="Password: ", stream=None)

        print(f"Username: {username}\nPassword: {password}")
