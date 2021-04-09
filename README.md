# py-PDf
py-PDf is a pure-python based library that exposes API endpoints to perform various PDF operations such as splitting, merging together, watermarking, converting Microsoft docs to PDFs. It can also add password to PDF files.

# Description
py-PDf is a fast and robust library written in python. It exposes various endpoints to PDF operations. py-PDf comes as a docker image and can be provides rest apis as containerized app, that allows it to easily deployed in linux containers system like Kubernetes or Azure Web app on Linux. 
#### Infra flexibility
Since library comes as a docker image, it can be hosted on your local platform or any other public cloud such as AWS or Azure. 
#### Easy and Fast Deployment Model
py-Pdf is easily available from Docker hub. Hence DevOps pipelines can pull the image directly and spin up the containers in feww seconds. 
#### Control On Infra Scaling
You can spin up as many continers (pods in case of Kubernetes) as possile based on Node comuting size.
#### Data Security
py-PDf doesn't store any data sent by consumers. It doesn't have any persistant storage and works in complete isolation; it is deployed in your own Infra/Cloud Subscription so that you have a better control on memory and CPU utilization.
#### Free PDF operations
There is no limitation on number of transactions with API. Since it is based on open source libraries, you can develop as many PDF as you want with almost zero operational cost.
You might need to endure Infra cost for hosting the API.
#### Fast response and less netwrok latency
Since you've a complete authority on how and where py-PDf should be deployed, you can always host it in your nearest data center(region) to reduce the network latency and provide fastest response to your application consumers.

# Understanding API endpoints:

# Installing

#### Local Machine Set Up

#### Azure Web App in Linux Deployment

# Dependencies
- Docker v20.x
- Linux containers

# Author
 Pushpdeep Gupta (pushpdeepamity@gmail.com)
 Git Username: https://github.com/PushpMicrosoft123

# Version History
- 1.0 Initial release

# License
This project is licensed under the [MIT LICENSE](https://choosealicense.com/licenses/mit/)

