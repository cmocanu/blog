---
title: URL Shortener
date: '2012-04-24'
slug: url_shortener
---


Building a simple URL shortener
------------
Following the rant on how learning programming should be a more practical, code first experience, I created a small [project](https://github.com/cmocanu/url_shortener) to better illustrate my vision. It is a very simple API for a URL shortener created in Flask. The API is not implemented, but there are tests provided and I will also provide a separate solution to compare against your own.

Implementing this API will teach you a few important concepts:

- the basics of how the web works, GET and POST requests and status codes

- the fundamental pieces of the backend of a web app, such as routing

- working with Docker containers

- basics of using the Flask framework


The setup
------------
This project is designed to be run and tested in a docker container. Well, two actually. What this means is that you don't need to have python or flask installed on your operating system to be able to complete the exercises. Still, you'll need [docker](https://www.docker.com/community-edition) and docker-compose.

You don't need to understand how docker works, but you'll need a few basic commands.

To run the server, execute:
~~~bash
$ link_shortener: docker-compose up --build
~~~

This will run the two docker containers, web and nginx. To see them, run docker ps:
~~~bash
$ link_shortener: docker ps
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS              PORTS                         NAMES
b9236681ed18        linkshortener_nginx   "nginx -g 'daemon ..."   15 seconds ago      Up 14 seconds       0.0.0.0:80->80/tcp, 443/tcp   linkshortener_nginx_1
7602d01a0fcc        linkshortener_web     "/usr/local/bin/gu..."   16 seconds ago      Up 14 seconds       8000/tcp                      linkshortener_web_1
~~~

To run the tests, you need to run the nose2 command inside the web container (while the containers are running, so do thi from a different terminal tab).

~~~bash
$ link_shortener: docker exec -it 7602d01a0fcc nose2
.......
----------------------------------------------------------------------
Ran 7 tests in 0.023s

OK
~~~

Of course, not your all tests will pass in the beginning.

You can interact with the service using `curl` to make GET and POST requests. I recommend using `curl` in the beginning to see what your code is actually doing, not just relying on the tests. For example:

~~~bash
$ link_shortener: curl http://0.0.0.0/ping
pong
~~~


HTTP
------------

Hyper Text Transfer Protocol (HTTP) is the protocol that makes the web work. It's based on HTTP Requests and Responses.

The most basic types of requests are **GET** and **POST**.

A **GET** result just asks for some data from the server by giving a URL and a list of params. For example, when you go to [this](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) article you do a GET request to https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol and no params.

A **POST** request is used to send data to the server, such as sending a username and password for logging in. You can read more about HTTP Requests [here](https://www.w3schools.com/tags/ref_httpmethods.asp).

Each HTTP request sends back an HTTP Response, that contains (among others) a body and a status code. For example, for the wikipedia article linked earlier, the response body is the HTML code of the page, and the status code is 200 (meaning OK). Should the page not exist, you would get status code 404 (Not found).

You can also use curl to create HTTP. For example:

~~~bash
curl -L http://wikipedia.com
~~~

Makes a GET request to wikipedia and shows you the response, which is the actual page (html, css, js).

Requirements
------------
You are going to build simplified version of an URL shortener service (not the web app itself), that should implement the following interface:

~~~bash
GET /ping
Should respond with 'pong'

This method is already implemented as an example and the corresponding test should pass.
This is a basic health check that the server is running.
~~~
~~~bash
POST /ping
Should respond with 'postpong'

Just making sure you can figure out POST requests too.
The body of the request should be ignored.
~~~
~~~bash
POST 'url=$URL' /add_url
Should respond with a string that represents the short link.
Should return a 500 status code if the URL is invalid.

The URL should be a valid http or https url.
The returned string should have a length of 10 and only contain lowercase letters and digits.
~~~
~~~bash
GET /$short_url
Should respond with the URL corresponding to the $short_url.
Should respond with a status code 404 if $short_url does not exist.

This is the way a shortened URL is visited.
~~~
~~~bash
GET /info/$short_url
Should respond a JSON with information about $short_link:
{
  url: the original url,
  short_url: the short_url,
  visits: the number of times the short link was visited

}
Should respond with a status code 404 if $short_url does not exist.

This is the way a shortened URL is visited.
~~~

Tech tips
------------

Flask routing:

Accept GET and POST requests:
~~~python
@app.route('/test', methods=['GET', 'POST'])
~~~

Tell GET and POST requests apart:
~~~python
request.method == 'GET' # or 'POST'
~~~

Create dynamic route
~~~python
@app.route('/<url>', methods=['GET'])
def visit_url(url):
  return url
~~~

Return HTTP error code. Default is 200 (HTTP OK).
~~~python
@app.route('/<url>', methods=['GET'])
def visit_url(url):
  return 'Error', 404 # Returns 404 Not Found error code
~~~

Further steps
------------

If you have completed the project and all tests are passing, but want to dig deeper, I suggest reading [this](https://www.interviewcake.com/question/java/url-shortener) for more ideas of features, or trying to implement a UI for it. I made a [script](http://jsfiddle.net/rovL5qdu/) that just calls /ping if you want to play around with it. You'll need to install [CORS](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi?hl=en) for it to work, though, and obviously the docker containers need to be running. Be careful, it breaks some sites when it's activated.
