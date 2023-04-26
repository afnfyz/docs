## Notes from the Postman Academy.

[Link to Postman Academy](https://academy.postman.com/)

### What is Postman?

"Postman is an API platform for building and using APIs. Postman simplifies each step of the API lifecycle and streamlines collaboration so you can create better APIs faster, and consume them with ease."

**cURL vs Postman**
<img width="1020" alt="image" src="https://user-images.githubusercontent.com/124072294/234708467-ecc82de3-188f-4f39-b25d-2e1e34d42a6c.png">

<img width="1030" alt="image" src="https://user-images.githubusercontent.com/124072294/234708551-b3100aa3-377f-472a-9e5f-25f7350c94b7.png">


**Reponse Status Codes:**

<img width="719" alt="image" src="https://user-images.githubusercontent.com/124072294/234711818-ae27f9a9-ba1f-4ceb-8187-8aa8e5fa6f29.png">

**Query Parameter Syntax**

Query parameters are added to the end of the path. They start with a question mark ?, followed by the key value pairs in the format: <key>=<value>. For example, this request might fetch all photos that have landscape orientation:

GET https://some-api.com/photos?orientation=landscape

If there are multiple query parameters, each is separated by an ampersand &. Below, two query parameters to specify the orientation and size of photos to be returned:

GET https://some-api.com/photos?orientation=landscape&size=500x400