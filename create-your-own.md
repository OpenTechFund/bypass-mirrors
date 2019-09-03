# Create your own bypass mirrors setup

You can create your own set of bypass mirrors using the following tools:
- The Bypass Censorship browser extension
- A set of mirrors hosted on github
- [proxy automation tool](https://github.com/OpenTechFund/otf_proxy)
- Instructions for creating mirrors (below)
- [python-mirror docker container](https://hub.docker.com/r/pearlbear/python-mirror)

## Create the mirrors:

Most of the mirrors are "mirrors" in that they are not hosted mirrors of the sites targeted. Most are CDN proxies. Instructions for actual mirrors are at the end of this section.

We used [AWS CloudFront](https://aws.amazon.com/cloudfront/), [Azure CDN](https://azure.microsoft.com/en-us/services/cdn/), and [Fastly](https://www.fastly.com/) to create CDN distributions of targeted sites. So accounts will be required for each of these services.

The CDN proxies were created, and the distribution URLs, (e.g. d3qinv6vsiufbn.cloudfront.net) were added to the bypass-mirrors json document via an automated system. The code for that is found under "proxy_automation" in [this](https://github.com/OpenTechFund/otf_proxy) GitHub repo. Detailed instructions for using that tool are in that repo. Using that repo is not required - you can set up the proxies manually on your own, and add them manually to your mirror JSON document.

### Using actual mirrors

Some sites do not proxy well via CDN. Primarily, if a site has an automatic redirect to a url that contains a directory (e.g. https://www.example.org -> https://www.example.org/something,) these CDN proxies will fail. In addition, if there are absolute URL references in the content, instead of relative, that will mean that links clicked will try to retrieve the targeted site, and if that site is censored, that page will not be able to be retrieved.

So the best strategy for these sites is to use a docker container, which has a python script which will mirror a site, and replace relative links on the fly. You can host this site on AWS ECS (use Fargate) or implement on a server.

## Clone the Extension

The bypass mirrors browser extension is [here](https://github.com/OpenTechFund/bypass-censorship-extension).
