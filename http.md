# S.O.L.I.D principles    
[Home](./README.md)  
[Reference](https://www.baeldung.com/java-http-request)  

## Creating a request and then connecting to the http connecrtion   
```
URL url = new URL("http://numbersapi.com");
HttpURLConnection con = (HttpURLConnection) url.openConnection();
con.setRequestMethod("GET");
```

If you want to customize the connection then just type
```
HttpConnection connection
```

## Adding request parameters  
```
If we want to add parameters to a request, we have to set the doOutput property to true, then write a String of the form param1=value¶m2=value to the OutputStream of the HttpUrlConnection instance:

```
