[PHP SESSION](http://php.net/manual/en/session.configuration.php)
HTTP请求出现异常，一定要先看协议头．
然后在找其他原因
ｓｅｓｓｉｏｎ，的域名问题设置很重要
```
session.save_path	""	PHP_INI_ALL	 
session.name	"PHPSESSID"	PHP_INI_ALL	 
session.save_handler	"files"	PHP_INI_ALL	 
session.auto_start	"0"	PHP_INI_PERDIR	 
session.gc_probability	"1"	PHP_INI_ALL	 
session.gc_divisor	"100"	PHP_INI_ALL	Available since PHP 4.3.2.
session.gc_maxlifetime	"1440"	PHP_INI_ALL	 
session.serialize_handler	"php"	PHP_INI_ALL	 
session.cookie_lifetime	"0"	PHP_INI_ALL	 
session.cookie_path	"/"	PHP_INI_ALL	 
session.cookie_domain	""	PHP_INI_ALL	 
session.cookie_secure	""	PHP_INI_ALL	Available since PHP 4.0.4.
session.cookie_httponly	""	PHP_INI_ALL	Available since PHP 5.2.0.
session.use_strict_mode	"0"	PHP_INI_ALL	Available since PHP 5.5.2.
session.use_cookies	"1"	PHP_INI_ALL	 
session.use_only_cookies	"1"	PHP_INI_ALL	Available since PHP 4.3.0.
session.referer_check	""	PHP_INI_ALL	 
session.entropy_file	""	PHP_INI_ALL	 
session.entropy_length	"0"	PHP_INI_ALL	 
session.cache_limiter	"nocache"	PHP_INI_ALL	 
session.cache_expire	"180"	PHP_INI_ALL	 
session.use_trans_sid	"0"	PHP_INI_ALL	PHP_INI_ALL in PHP <= 4.2.3. PHP_INI_PERDIR in PHP < 5. Available since PHP 4.0.3.
session.bug_compat_42	"1"	PHP_INI_ALL	Available since PHP 4.3.0. Removed in PHP 5.4.0.
session.bug_compat_warn	"1"	PHP_INI_ALL	Available since PHP 4.3.0. Removed in PHP 5.4.0.
session.hash_function	"0"	PHP_INI_ALL	Available since PHP 5.0.0.
session.hash_bits_per_character	"4"	PHP_INI_ALL	Available since PHP 5.0.0.
url_rewriter.tags	"a=href,area=href,frame=src,form=,fieldset="	PHP_INI_ALL	Available since PHP 4.0.4.
session.upload_progress.enabled	"1"	PHP_INI_PERDIR	Available since PHP 5.4.0.
session.upload_progress.cleanup	"1"	PHP_INI_PERDIR	Available since PHP 5.4.0.
session.upload_progress.prefix	"upload_progress_"	PHP_INI_PERDIR	Available since PHP 5.4.0.
session.upload_progress.name	"PHP_SESSION_UPLOAD_PROGRESS"	PHP_INI_PERDIR	Available since PHP 5.4.0.
session.upload_progress.freq	"1%"	PHP_INI_PERDIR	Available since PHP 5.4.0.
session.upload_progress.min_freq	"1"	PHP_INI_PERDIR	Available since PHP 5.4.0.
session.lazy_write	"1"	PHP_INI_ALL	Available since PHP 7.0.0.
```
