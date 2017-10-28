# File Upload

![](/assets/AutomataWork %2824%29.png)

#### Intro:

File upload will have an option to upload files on either server or amazon s3 storage.

### Total Tasks

* [ ] API to define virtual container.
* [ ] Virtual container would be nothing but just an API Virtual path to define some properties etc for uploading.
* [ ] Option to define max file size, min file size and allowed MIME types to a container.
* [ ] If container has MIME type of image container will have an option to crop the image in different sizes before uploading
* [ ] Image Model for storing the metadata of uploaded file.
* [ ] API to generate signed image.
* [ ] GraphQL schema for image type to fetch image based on size of image like
  ```
  {
  imageType: "medium" //WIll then fetch the image link for medium size images.
  }
  ```
* [ ] CloudFront Integration for supporting CDN with file.

##### FEATURES

| Work | Design Time | Logic TIme | Priority |
| :--- | :--- | :--- | :--- |
| API to define and create Virtual Container |  | 6 |  |
| API for Uploading and Removing et files from container. |  | 6 |  |
| API to define container for max file Size, MIME Type etc |  | 6 |  |
| GraphQL Schema to fetch all image types. |  | 3 |  |
| Cloud Front integration for supporting CDN capabilities, SIgned Image etc |  | 2 |  |
|  |  |  |  |

#### SCREENS

| SCREEN | COMMENT | MERGE\_STATUS |
| :--- | :--- | :--- |
|  |  |  |



