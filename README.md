# bypass-mirrors
Mirror list for censorship bypass.

### v1 format

```
{
    "main_domain": "domain.com",
    "available_mirrors": [
    "domain1.global.ssl.fastly.net",
    "d3anwerwedwdwep65.cloudfront.net"
    ],
    "available_onions": ["dewedasdarj4cele.onion"],
    "available_ipfs_nodes": ["QmQ9GrEC5MVVb69HE2thmxNdSazNGjXdi6YLeQT3EULjVu"]
}
```
### v2 Format

```
{
    "main_domain": "domain.com,
    "available_alternatives": [
        {
            "proto": "http",
            "type": "mirror",
            "created_at": "2020-07-08 11:39:07.637811",
            "url": "http://lala.test.com"
        },
        {
            "proto": "tor",
            "type": "eotk",
            "created_at": "2020-07-08 11:43:11.676377",
            "url": "http://lalalslsksjsusheehjdfdjasd.onion"
        },
        {
            "proto": "https",
            "type": "ipfs",
            "created_at": "2020-12-12 11:23:23.23322",
            "url": ""
        }
    ]
}
```