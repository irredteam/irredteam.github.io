---
layout: default
published: true
---

# رمزنگاری

## وبسایت های کاربردی

| آدرس | توضیح |
| :--- | :--- |
| https://www.dcode.fr/ | رمزنگاری و رمزگشایی |
| https://crackstation.net/ | رمزگشایی |
| https://gchq.github.io/CyberChef/ | رمزنگاری و رمزگشایی و ... |


## رمز گشایی Fernet

```text
https://asecuritysite.com/encryption/ferdecode
```

یا 
  
```text
from cryptography.fernet import Fernet
key = ""
token = ""
cipher = Fernet(key)
decoded = cipher.decrypt(token)
```
