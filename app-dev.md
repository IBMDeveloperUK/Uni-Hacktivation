# application development hacks #

## NHS Digital public data ##
[all published data](https://digital.nhs.uk/search/document-type/publication/publicationStatus/true?sort=date&area=all)

## Australia Institute of Health and Welfare public data ##
[current published data](https://www.aihw.gov.au/reports-data/latest-reports)

## cloudant tutorials, blogs, etc ##
https://blog.cloudant.com/

## cloudant samples ##
+ [Movies demo](https://examples.cloudant.com/movies-demo/_all_docs?include_docs=true&limit=100)
+ [Animals](https://examples.cloudant.com/animaldb/_all_docs?include_docs=true&limit=100)

## generating sample JSON datasets ##

[datamaker](https://medium.com/@glynn_bird/generating-sample-data-for-a-json-data-store-1eb45604691e)

## quick and dirty website ##

1. install the `ibmcloud` [cli](https://cloud.ibm.com/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)
1. create a project folder for your website
1. create or copy into the folder the html and other resources (images, css, etc) you want serve from your website 
  *make sure there is an _index.html_ file*
1. open a commnd terminal and change directory to your project directory
1. login to your IBM Cloud account: 
  `ibmcloud login`
1. use the CloudFoundry mode to target your cloud organisation and space to host your website:
  `ibmcloud target --cf`
1. get a list of supported runtime buildpacks: 
  `ibmcloud cf buildpacks` -- look for _staticfile_buildpack_
1. pick a hostname for your website - `<mysitename>`
1. push the website to the cloud: 
  `ibmcloud cf push -b staticfile_buildpack -m 48M <mysitename>`
1. once the push completes, look for the fully-qualified domain name (FQDN) of your website - 
  `routes: <mysitename>[.something].mybluemix.net`
1. check in  browser: 
  `https://<mysitename>[.something].mybluemix.net`
