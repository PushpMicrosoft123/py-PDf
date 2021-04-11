# py-PDf
py-PDf is a pure-python based library that exposes API endpoints to perform various PDF operations such as splitting, merging together, watermarking, converting Microsoft docs to PDFs. It can also add password to PDF files.

# Description
py-PDf is a fast and robust library written in python. It exposes various endpoints to PDF operations. py-PDf comes as a docker image and can be provides rest apis as containerized app, that allows it to easily deployed in linux containers system like Kubernetes or Azure Web app on Linux. 
#### Infra flexibility
Since library comes as a docker image, it can be hosted on your local platform or any other public cloud such as AWS or Azure. 
#### Easy and Fast Deployment Model
py-Pdf is easily available from Docker hub. Hence DevOps pipelines can pull the image directly and spin up the containers in feww seconds. 
#### Control On Infra Scaling
You can spin up as many py-PDf continers as possile based on nodes availability or compute size.
#### Data Security
py-PDf doesn't store any data sent by consumers. It doesn't have any persistant storage and works in complete isolation; it is deployed in your own Infra/Cloud Subscription so that you have a better control on memory and CPU utilization.
#### Free PDF operations
There is no limitation on number of transactions with API. Since it is based on open source libraries, you can develop as many PDF as you want with almost zero operational cost.
You might need to endure Infra cost for hosting the API.
#### Fast response and less netwrok latency
Since you've a complete authority on how and where py-PDf should be deployed, you can always host it in your nearest data center(region) to reduce the network latency and provide fastest response to your application consumers.

#### Smooth Integration
py-PDf provides all capabilities in the form of exposed APIs. Hence, it can easily be integrated with any application irrespective of which language they have implemented with. All we have to do is to call http endpoints to get service.

# Understanding API endpoints:
 With the initial release 1.0 py-PDf exposes 4 endpoints for testing, watermarking, merging and converting docs to PDF.
- {your-endpoint}/test
 Get method to test if server is running. No Request payload is required
 **Returns** the positive response with 200.
- {your-endpoint}/add-watermark
 This Post method adds watermark to the uploaded PDF. Methods requires two form-data values as inout:
  1. oFile: PDF file that needs to be watermarked
  2. wFile: A watermark pdf file to be used as a watermark.
 **Returns** the final PDF as stream object.
- {your-endpoint}/convert-to-pdf
 This POST method converts Microsft word document to PDF.
 Methods requires one form-data input:
  1. file: file with doc/docx extension.
**Returns** the converted PDF as stream object
- {your-endpoint}/merge-pdfs
 Post method provides cosumers to merge their PDFs into single file. It loads files directly from blob. Method requires list of PDF blob Uris in to be merged into single PDF.
 **Sample: ** {
    "url_list": ["PDF_Blob_URI_WithAccessToken1", "PDF_Blob_URI_WithAccessToken2"]
}
**Returns** the final PDF as stream object.

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
#### Python app deployment with Azure Web App for Linux
Make sure you have a valid Azur subscription:
Please follow below steps:
 1. Create a Web App resource:

    ![image](https://user-images.githubusercontent.com/45087848/114273519-f210d400-9a37-11eb-84b2-d55758bfd070.png)
 2. Provide basic information. Make sure you enable Docker Container:
 
    ![image](https://user-images.githubusercontent.com/45087848/114273687-af9bc700-9a38-11eb-82b7-aac9d1ca2397.png)
 3. Fill the Docker deatils as below:
 
    ![image](https://user-images.githubusercontent.com/45087848/114273738-ee318180-9a38-11eb-93c7-0c83306d2a1e.png)
 4. Create App:
 
    ![image](https://user-images.githubusercontent.com/45087848/114273831-49637400-9a39-11eb-8c13-9964366cfc5e.png) 
 5. App service will instantiate a Linux continer using py-PDf image:
 
 6. Set WEBSITES_PORT as 8083 as shown below:
 
    ![image](https://user-images.githubusercontent.com/45087848/114274001-1d94be00-9a3a-11eb-9d53-86a36992a645.png)
 7. Access API using app service URL field:
 
    ![image](https://user-images.githubusercontent.com/45087848/114274091-73696600-9a3a-11eb-9e5d-9a846f53f0e5.png)

#### Deploy on Kubernetes
Please follow steps [here](https://docs.docker.com/desktop/kubernetes/)

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

# License
This project is licensed under the [MIT LICENSE](https://choosealicense.com/licenses/mit/)

