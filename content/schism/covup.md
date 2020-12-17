+++
categories = ["covid","scripts","python","service"]
coders = []
date = 2020-06-11T12:30:35+05:30
description = "Get all the relevant pandemic related stats of the concerned districts first thing in the morning."
github = ["https://github.com/xfurna/CoVup/"]
image = "https://raw.githubusercontent.com/xfurna/xfurna.github.io/master/static/project_logos/covup.jpg?token=AG5NBSJVCWURK5GXHB4MFDS7MEULQ"
title = "CoVup Setu"
type = "post"
+++

Because services that have `setu` in their names are rad' cool.


## Github/CoVup repository


```bash
├── meta.json
├── README.md
├── scripts
│   ├── main.py
└── templates
    ├── announce.txt
    └── subscribers.txt
```


I have made such arrangements (using [WayScript](https://wayscript.com/)) that the script `scripts/main.py` would trigger itself off every day and send an email to all the subscribers regarding the latest CoV pandemic stats about their district (like active cases, confirmed cases, recovered cases and deceased cases).


## How to subscribe


You can subscribe to the service by opening an issue on this repository. Make sure to give following details in the description-
```json
"name": "xxx",
"email" : "xxx@xxx.xxx",
"district" : "xxx",
"state" : "xxx"
```


If you have privacy concerns, you can share your details with me on [telegram](https://t.me/xfurna), privately.


**Note:** You can make muliple subscriptions too.


## Contributions


Are welcome.


<hr>


**Courtesy:** [covid19india/api](https://github.com/covid19india/api)
