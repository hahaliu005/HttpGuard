http-guard
==========

This project is reference of : https://github.com/centos-bz/HttpGuard

Install Requirements:
---
```
Openresty

php php-gd
```

Install
---
```
git clone https://github.com/hahaliu005/HttpGuard.git
cd captcha && php getImg.php
```

add code to nginx.conf http area
```
lua_package_path "/data/www/waf/?.lua";
lua_shared_dict guard_dict 100m;
lua_shared_dict dict_captcha 70m;
init_by_lua_file '/data/www/waf/init.lua';
access_by_lua_file '/data/www/waf/runtime.lua';
lua_max_running_timers 1;
```
