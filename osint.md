---
layout: default
published: true
---

# ارزیابی اطلاعات از منابع آشکار یا OSINT

## ابزار های کاربردی

| آدرس | توضیح |
| :--- | :--- |
| https://osintframework.com/ | فریمورک osint  |
| https://github.com/jivoi/awesome-osint | منابع osint |
| https://start.me/p/rx6Qj8/start-page | منابع osint |
| https://censys.io/ | موتور جست و جو دستگاه های متصل به وب  |
| https://shodan.io/ | موتور جست و جو دستگاه های متصل به وب  |
| https://yasiv.com/youtube# | ارزیابی ویدیو های youtube |
| https://ohshint.gitbook.io/ | کتابچه آموزشی osint |
| https://epieos.com/| اکانت های مرتبط با ایمیل مانند skype  |







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

./gitgot.py -q example.com

./gitgot.py -q example.com -u https://git.example.com

./gitgot.py -q "org:github cats"

```

## ارزیابی اطلاعات برد های مدیریت پروژه

```text
inurl:https://trello.com AND intext:@gmail.com AND intext:password
inurl:https://trello.com AND intext:ftp AND intext:password
inurl:https://trello.com AND intext:ssh AND intext:password
inurl:jira AND intitle:login AND inurl:[company_name]
```

## جمع آوری ایمیل های دامین

```text
python3 theHarvester.py -d sbmu.ac.ir -b all -l 200
```

## فریمورک osint

https://www.spiderfoot.net/documentation/

### استفاده از طریق وب

```text
python3 sf.py -l 127.0.0.1:8070
```

### جمع آوری ایمیل های دامین

```text
python3 sf.py -m sfp_spider,sfp_hunter,sfp_fullcontact,sfp_pgp,sfp_clearbit,sfp_emailformat,sfp_email -s tesla.com -q -F EMAILADDR
```

### ارزیابی اطلاعات اکانت های کاربر

```text
python3 ./sf.py -m sfp_accounts -s "elonmusk" -q
```

### ارزیابی اطلاعات metadata فایل های دامین

```text
python3 ./sf.py -m sfp_intfiles,sfp_spider,sfp_filemeta -s tesla.com -q -F RAW_FILE_META_DATA
```
