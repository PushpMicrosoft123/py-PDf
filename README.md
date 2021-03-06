# py-PDf
py-PDf is a pure-python based library that exposes API endpoints to perform various PDF operations such as splitting, merging together, watermarking, converting Microsoft docs to PDFs. It can also add password to PDF files.

# Description
py-PDf is a fast and robust library written in pure python. It exposes several endpoints to perform PDF operations. py-PDf comes as a docker image and can be hosted as a containerized rest api on linux containers supported by your local desktop, Kubernetes, Azure Web app and various app hosting environments on public clouds. 

#### Infra flexibility
Since library comes as a docker image, it can easily be hosted on linux containers supported by local platform or any other public cloud such as AWS or Azure.

#### Easy and Fast Deployment Model
py-Pdf is easily available from Docker hub. Hence DevOps pipelines can pull the image directly and spin up the containers in feww seconds. 

#### Control On Infra Scaling/ No of service containers
You can spin up as many py-PDf continers as possile based on nodes availability or compute size.

#### Data Security
py-PDf doesn't store any data sent by consumers. It doesn't have any persistant storage and works in complete isolation; it is deployed in your own Infra/Cloud Subscription so that you have a better control on memory and CPU utilization.

#### Unlimited PDF operations
There is no limitation on number of transactions with API. Since it is based on open source libraries, you can develop as many PDF as you want with almost zero operational cost.
You might need to endure Infra cost for hosting the API.

#### Fast response and less network latency
Since you've a complete authority on how and where py-PDf should be deployed, you can always host it in your nearest data center(region) to reduce the network latency and provide fastest response to your application consumers.

#### Smooth Integration
py-PDf provides all the capabilities in the form of exposed APIs. Hence, it can easily be integrated with any application irrespective of the language they have implemented with. They are just required to call endpoints to avail the services.

# Understanding API endpoints:
 With the initial release 1.0 py-PDf exposes 4 endpoints for testing, watermarking, merging and converting docs to PDF.

- **{your-endpoint}/test**
 Get method to test if server is running. No Request payload is required
 **Returns** the positive response with 200.

- **{your-endpoint}/add-watermark**
 This Post method adds watermark to the uploaded PDF. Methods requires two form-data values as inout:
  1. oFile: PDF file that needs to be watermarked
  2. wFile: A watermark pdf file to be used as a watermark.
  **Returns** the watermarked PDF as stream object.

- **{your-endpoint}/add-text-watermark**
   This endpoint is capable of addig watermark as background text. Send watermark text of your choice not exceeding 20 characters. Parameters:
   1. wm_text: watermark text as part of form-data.
   2. file: a pdf file to be watermarked, send it as part of form-data.
 **Returns** the watermarked pdf as stream object.

- **{your-endpoint}/convert-to-pdf**
 This POST method converts Microsft word document to PDF.
 Methods requires one form-data input:
  1. file: file with doc/docx extension.
**Returns** the converted PDF as stream object

- **{your-endpoint}/merge-pdfs**
 Post method provides cosumers to merge their PDFs into single file. It loads files directly from blob. Method requires list of PDF blob Uris in to be merged into single PDF.
 **Sample: ** {
    "url_list": ["PDF_Blob_URI_WithAccessToken1", "PDF_Blob_URI_WithAccessToken2"]
}
**Returns** the final PDF as stream object.

- **{your-endpoint}//merge-streams-pdf**
 Post method merge PDF streams into single PDF file. The previous merge method reads pdfs from Blobs where as this method supports posting PDF files directly to server with payload. send multiple pdf files for merging in request form-data.
 **Returns** Merged PDF as stream object.
 
# Download From Docker Hub
  https://hub.docker.com/repository/docker/pushpdeep123456/py-nin-pdf
  or use command $ docker pull pushpdeep123456/py-nin-pdf:1.0
# Installing
Please note py-PDf exposes port 8083 from container, you can map your machine's port to hit the containers API as mentionned in local machine setup.

#### Local Machine Set Up
 - Make sure docker is installed on your machine, you can follow the download instructions [here](https://docs.docker.com/get-docker/)
 - Run $ docker run -dit -p 8083:8083 pushpdeep123456/py-nin-pdf:1.0 . This will deploy the docker containe using image.
 - Hit URL : http://localhost:8083/test. You must get success acknowledgement :
 {
    "data": "Your server is up and running."
 }
 - API is ready to serve your requests.

#### py-PDf deployment on cloud
This service can be hosted on a Linux continer by downloading latest image from docker hub/registry.
1. Please see Microsoft documentation on how to deploy Containerized app on Linux containers
2. Please see Microsoft docs on how to deploy docker image on AKS (Azure kubernetes services)
**Please note: App exposes port no 8083 inside the container. To access APIs, you can map this port to any available port on your hosting machine.**

# Dependencies
- Docker v20.x
- Linux container

# Author
 Pushpdeep Gupta (pushpdeepamity@gmail.com)
 Git Username: https://github.com/PushpMicrosoft123

# Contribution
 Currently, source code is not publicly available. To contribute please drop an email to pushpdeepamity@gmail.com.
 
# Version History
- 1.0 Initial release
- 1.0.1 Added capability of merging pdf files coming in request form-data.
- 1.0.2 A New watermark capability. You can now add watermark as a background text for your PDFs to preseve the copyright. 

# License
This project is licensed under the [MIT LICENSE](https://choosealicense.com/licenses/mit/)

