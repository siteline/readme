# How to make siteline

## Architecture
![](./art/siteline-structure.png)

## How to communicate between proxy and siteline servers
The proxy pulls messages from siteline servers by HTTP GET method.

The following request is used to get the information about the siteline server:
```
http://<ip>:<port>/about
```
The response body is json object, just like:
```
{
  "title": "news about sports",
  "abstract": "blabla"
}  
```

The following request format is used to get content(many URLs) from a siteline server:
```
http://<ip>:<port>/content?year=<year>&month=<month>&day=<day>&timezone=<timezone>
```

Here is an example:
```
http://127.0.0.1:5678/content?year=2016&month=5&day=24&timezone=Asia%2FShanghai
```

`year`, `month`, `day`, `timezone` must be given in the query params.It's highly recommended to get more info from http://momentjs.com/timezone . 


## License
MIT
