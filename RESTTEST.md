
If you are using [VS Code](https://code.visualstudio.com) and have the [REST Client extension](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) installed, the content below will help with troubleshooting [Declarative Onboarding](https://clouddocs.f5.com/products/extensions/f5-declarative-onboarding/latest/) and [Application Services](https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/). 

```text
#
# bigip address, username, and password are 
# retrieved from a .env file
#
# the format of the .env file looks like
# bigip1=0.0.0.0
# user=username
# password=yoursecretpassword
#

###
# @name dostatus
#
GET https://{{$dotenv bigip1}}/mgmt/shared/declarative-onboarding?show=full
Authorization: Basic {{$dotenv user}} {{$dotenv password}}
Content-Type: application/json

###
# @name analyticsstatus
#
GET https://{{$dotenv bigip1}}/mgmt/tm/analytics/global-settings HTTP/1.1
Authorization: Basic {{$dotenv user}} {{$dotenv password}} 

###
# @name as3status
#
GET https://{{$dotenv bigip1}}/mgmt/shared/appsvcs/declare
Authorization: Basic {{$dotenv user}} {{$dotenv password}}
Content-Type: application/json
```