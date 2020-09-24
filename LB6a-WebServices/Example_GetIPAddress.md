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

#### Use the Fetch API for *requesting* services
The necessary element for making HTTP requests is the **fetch API**. To use fetch in its most basic form, all we need to do is provide the URL to send our request to. Once the request has been made, a response will be returned that we can then process. 

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

Inside the script tag, add the following code that makes up our web request:
```
fetch("https://ipinfo.io/json")
  .then(function (response) {
    return response.json();
  })
  .then(function (myJson) {
    console.log(myJson.ip);
  })
  .catch(function (error) {
    console.log("Error: " + error);
  }); 
```

Once you have added these lines, save your changes and test your page in the browser. You won't see anything displayed on screen, but if you bring up the **Console** via your browser developer tools, you should see your IP address getting displayed.  

Now that we have our IP address getting displayed to our console, let's take a moment and revisit the code and see what exactly it is doing. 

With our first line of code,  
- we are calling fetch and providing ***the URL we want to make our request to***  
- The URL we send our request to is ipinfo.io/json  
- Once this line gets run, ***the service running on ipinfo.io will send us some data***  
- ***It is up to us to process that data***

How do we know that the IP address is going to be stored by the ip property from our returned JSON data? The easiest way is by referring to the ipinfo.io developer documentation! ***Every web service will have its own format for returning data when requested.***

#### Handle the *returned data* and display it
What we have right now is a blank page with our IP address being printed to the console. Let's go ahead and add the few missing details to get our current page looking like an example page.  

In our current HTML document, make the following changes/additions:

```
<!DOCTYPE html>
<html>

<head>
  <title>Display IP Address</title>
  ***<style>
    body {
      background-color: #FFCC00;
    }

    h1 {
      font-family: sans-serif;
      text-align: center;
      padding-top: 140px;
      font-size: 60px;
      margin: -15px;
    }

    p {
      font-family: sans-serif;
      color: #907400;
      text-align: center;
    }
  </style>***
</head>

<body>
  <h1 id=ipText></h1>
  <p>( This is your IP address...probably :P )</p>
  <script>
    fetch("https://ipinfo.io/json")
      .then(function (response) {
        return response.json();
      })
      .then(function (myJson) {
        document.querySelector("#ipText").innerHTML = myJson.ip;
      })
      .catch(function (error) {
        console.log("Error: " + error);
      });
  </script>
</body>

</html>

```







