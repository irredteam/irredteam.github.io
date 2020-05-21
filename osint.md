---
layout: default
published: true
---

# ارزیابی اطلاعات از منابع آشکار یا OSINT

## ابزار های کاربردی

| آدرس | توضیح |
| :--- | :--- |
| https://censys.io/ | موتور جست و جو دستگاه های متصل به وب  |
| https://shodan.io/ | موتور جست و جو دستگاه های متصل به وب  |



## ارزیابی اطلاعات SPF

```text
 dig txt secure-startup.com
 dig txt _dmarc.secure-startup.com
```

## ارزیابی اطلاعات مربوط به دامنه 

```text
python photon.py -u https://example.com -l 3 -t 100 --wayback
```

## ارزیابی اطلاعات اکانت های کاربر

```text
python3 sherlock <user>
```

## ارزیابی اطلاعات twitter

### کلیه توییت های حاوی لینک

```text
twint -u username --links include
```

### کلیه توییت ها با فیلتر بر روی بستر ارسال کننده 

```text
twint -u username --source "Twitter Web Client"
```

### جست و جو بر روی توییت های لیست ارسال کنندگان

```text
twint -s keyword --min-likes 5 --members-list "folder/user_list"
```

## ارزیابی اطلاعات instagram

```text
python3 main.py --username <username>
```


## ارزیابی اطلاعات git

```text
gitrob <username> or <git repo>
```

## جمع آوری ایمیل های دامین

```text
python3 theHarvester.py -d sbmu.ac.ir -b all -l 200
```

