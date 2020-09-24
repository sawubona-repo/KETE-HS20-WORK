### Example GetIPAddress - Making HTTP/Web Requests in JavaScript  

###### Last update: 24/9/20 dbe
</br>
The HTTP protocol provides a common language that allows your browser to communicate with all the servers that make up the internet. 
The requests your browser makes on your behalf using the HTTP protocol are known as HTTP requests, and these requests go well beyond simply loading a new page as you are navigating. 
A common (and whole lot more exciting!) set of use cases revolve around updating your existing page with data resulting from a HTTP request.

#### The Example
Reading (or even thinking) about the HTTP and requests is boring. Thus, we are going to  building a small example. The example will look as follows:  
* We have some JavaScript that makes an HTTP request to a service (ipinfo.io) that returns a whole bunch of data about your connection. 
* Using JavaScript, we process all that returned data and surgically pinpoint the IP address that we display here.

#### Meet Fetch
The newest kid on the block for making HTTP requests is the **fetch API**. To use fetch in its most basic form, all we need to do is provide the URL to send our request to. Once the request has been made, a response will be returned that we can then process. 

See the code skeleton below. If you want to follow along, create a new HTML document and add the following markup into it:

```
<!DOCTYPE html>
<html>

<head>
  <title>Display IP Address</title>
</head>

<body>

  <script>

  </script>
</body>

</html> 
```



