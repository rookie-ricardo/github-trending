### Github trending

![github.png](http://upload-images.jianshu.io/upload_images/2040047-113772827550d86c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

This project is a GitHub trending API power by FastAPI and Scrapy parsel.
It was deployed on Vercel.

---

#### All the requests main adrress is this:https://trend.doforce.xyz

[FastAPI Docs](https://trend.doforce.xyz/docs)

#### Get the trending repositories

request address like this:

> /repo

##### Parameters

| Name  | Type   | Description                                                  |
| ----- | ------ | ------------------------------------------------------------ |
| lang  | string | optional, default is "", the language of trending repository |
| since | string | optional，default is daily, daily/weekly/monthly             |

For example request this address:
https://trend.doforce.xyz/repo?lang=java&since=weekly

return:

```json
//status code: 200
// up to 25 items
[
    {
        "repo": "/StarRocks/starrocks",
        "desc": "StarRocks, a Linux Foundation project, is a next-generation sub-second MPP OLAP database for full analytics scenarios, including multi-dimensional analytics, real-time analytics, and ad-hoc queries. InfoWorld’s 2023 BOSSIE Award for best open source software.",
        "lang": "Java",
        "stars": 6338,
        "forks": 1437,
        "build_by": [
            {
                "avatar": "https://avatars.githubusercontent.com/u/57167462?s=40&v=4",
                "by": "/amber-create"
            },
            {
                "avatar": "https://avatars.githubusercontent.com/u/98087056?s=40&v=4",
                "by": "/evelynzhaojie"
            },
            {
                "avatar": "https://avatars.githubusercontent.com/u/4351040?s=40&v=4",
                "by": "/sduzh"
            },
            {
                "avatar": "https://avatars.githubusercontent.com/u/104624482?s=40&v=4",
                "by": "/EsoragotoSpirit"
            },
            {
                "avatar": "https://avatars.githubusercontent.com/u/34912776?s=40&v=4",
                "by": "/stdpain"
            }
        ],
        // How many stars did it gain this week/day/month
        "change": 619
    }
]
```

#### Get the trending developers

request address like this:

> /user

##### Parameters

| Name        | Type   | Description                                                                                |
| ----------- | ------ | ------------------------------------------------------------------------------------------ |
| lang        | string | optional, default is "", the language of trending repository                               |
| since       | string | optional，default is daily, daily/weekly/monthly                                           |
| sponsorable | string | optional，default is "", Whether the developer was sponsored, "1" is true, others is false |

For example request this address:
https://trend.doforce.xyz/user?lang=java&since=weekly

return:

```json
//status code: 200
// up to 25 items
[
    {
        // developer's GitHub avatar
        "avatar": "https://avatars.githubusercontent.com/u/322311?s=96&v=4",
        // developer's nickname
        "name": "Ben McCann",
        // developer's GitHub name
        "github_name": "/benmccann",
        "popular": {
            // developer's popular repository
            "repo": "/benmccann/NameMatching",
            // developer's popular repository description
            "desc": "My entry (Yet Another Team Challenge) to MITRE's name matching competition"
        }
    }
]
```

### Get all the avialiable trending languages in GitHub.

For example,request this address:
https://trend.doforce.xyz/lang

return:

```json
//status code: 200
// about 700 items
[
    {
        // The display language name
        "label": "Unknown languages",
        // the language name which is used to search repositories and developers
        "key": "unknown"
    }
]
```

### Exception

If the server does not get the resources, or the query parameters you input don't match anything, the response will be like:

```
//status code: 200
[]
```

#### Maintenance

If some of the api can not be used, please contact me with email:`doforce@pm.me`,I will modify the problem as soon as possible,thank you!
