Related Redmine
===============

Show Redmine issues related by the displayed page.
You can watch the progress of your own Redmine project from wiki, mail, github with one click.


[Chrome Web Store](https://chrome.google.com/webstore/detail/related-redmine/kmgkdpnmpjmncggngjcinmkfacbgaecj)



![Related Redmine](img/tile.png)

![Screenshot 1](img/screenshot.png)


Note: Needs Redmine Server Settings
```
# allow this extension only
Header always set Access-Control-Allow-Origin "chrome-extension://kmgkdpnmpjmncggngjcinmkfacbgaecj"
```
or
```
# allow all
Header always set Access-Control-Allow-Origin "*"
```
in apache conf.



## Setting Images

![Custom Feild Setting](img/redmine-custom-field.png)

![Related Redmine Setting](img/related-redmine-settings.png)


## Sample Settings


### Github

| Name               | Value         |
| ------------------ | ------------- |
| Redmine url        | https://redmine.example.com/ |
| Trigger page url   | https://github.com/user/myproject/issues |
| Trigger pattern    | issues/([0-9]+)      |
| API KEY            | xxxxxxxxxxxx (see redmine's my page)  |
| Redmine parent url | https://redmine.example.com/projects/myproject/issues.xml?status_id=*&cf_1=%value% |
| Redmine child url  | https://redmine.example.com/projects/myproject/issues.xml?status_id=*&parent_id=%value% |

`1` of cf_1 is custom field id.


### Gmail (for private ticket in all projects)

| Name               | Value         |
| ------------------ | ------------- |
| Trigger page url   | https://mail.google.com/ |
| Trigger pattern    | /([^/]+)$      |
| Redmine parent url | https://redmine.example.com/issues.xml?status_id=*&cf_1=%value% |
| Redmine child url  | https://redmine.example.com/issues.xml?status_id=*&parent_id=%value% |


### Other BTS, Wiki, etc.

| Name               | Value         |
| ------------------ | ------------- |
| Trigger page url   | https://mybts.example.com/ |
| Trigger pattern    | issues/([0-9a-zA-Z]+)      |


## Note

Not support to link of multiple repositories, because not suport in Redmine REST API.


## Logo Licence

Redmine Logo is Copyright (C) 2009 Martin Herr and is licensed under the Creative Commons Attribution-Share Alike 2.5 Generic license.
