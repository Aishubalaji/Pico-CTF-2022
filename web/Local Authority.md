### THE CHALLENGE:

```
Can you get the flag?
Go to this website(http://saturn.picoctf.net:51419/) and see what you can discover.
```
viewing the source code of [login.php](http://saturn.picoctf.net:51419/login.php) we can see the script for checking the username and password

```js
    <script type="text/javascript">
      function filter(string) {
        filterPassed = true;
        for (let i =0; i < string.length; i++){
          cc = string.charCodeAt(i);
          
          if ( (cc >= 48 && cc <= 57) ||
               (cc >= 65 && cc <= 90) ||
               (cc >= 97 && cc <= 122) )
          {
            filterPassed = true;     
          }
          else
          {
            return false;
          }
        }
        
        return true;
      }
    
      window.username = "asd";
      window.password = "asd";
      
      usernameFilterPassed = filter(window.username);
      passwordFilterPassed = filter(window.password);
      
      if ( usernameFilterPassed && passwordFilterPassed ) {
      
        loggedIn = checkPassword(window.username, window.password);
        
        if(loggedIn)
        {
          document.getElementById('msg').innerHTML = "Log In Successful";
          document.getElementById('adminFormHash').value = "2196812e91c29df34f5e217cfd639881";
          document.getElementById('hiddenAdminForm').submit();
        }
        else
        {
          document.getElementById('msg').innerHTML = "Log In Failed";
        }
      }
      else {
        document.getElementById('msg').innerHTML = "Illegal character in username or password."
      }
 ```
 There is a ``checkPassword`` function being used but where does it come from?
 
 It comes from [secure.js](http://saturn.picoctf.net:51419/secure.js) which is imported in login.php
 
 We get the correct creds from secure.js
 
 ```
 username: admin
 password: strongPassword098765
 ```
 Nice! now let's login with these creds
 
 **Flag**: picoCTF{j5_15_7r4n5p4r3n7_d6a44d91}
 
 Challenge link in Pico Gym: https://play.picoctf.org/practice/challenge/278?category=1&originalEvent=70&page=1
 
 
