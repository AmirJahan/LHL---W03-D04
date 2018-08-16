This morning we talked about networking in iOS as well as databases and server side matters. 

### NSURLSession
Basics of networking (Communication between two computers)
Protocols help organizing remote communications. 
A Protocol is a rule that computers should adhere to if they wish to speak to one another.


###	Protocols:
TCP/IP (Transmission Control Protocol / Internet Protocol) is the basic communication language or protocol of the Internet
HTTP: Hypertext Transfer Protocol 
FTP: File Transfer Protocol

Networking terminology: 
	Client	
	Server
	Request
	Response


Client: Makes a request to a host computer.
Host: Returns a response to the client.

Server-side vs client-side

HTTP
Verbs and status codes
	POST
	GET	
	PUT
	DELETE

HTTP responses have a standardized status code
HTTP Response Status Codes: 
	404 not found, 418 I'm a teapot, 401 forbidden,
	4XX - Bad, you did something wrong.
	5XX - Bad, Server error. The server did something wrong.
	2XX - Good, everything is as we wanted.
	3XX - Redirections.
	1XX - informational.
	6XX - They don't exist.


REST (Representation State Transfer) 
API is said to be RESTful when it conforms to the constraints of the REST architecture

A web api is a set of exposed endpoints we can make requests to to get data.

i.e.: http://firebase.io/myuser/myShopperApp/mynode

REST APIs make use of HTTP verbs and return JSON or XML 


What is XML 
<node name=“Eggs”>
      <name>Eggs</name>
      <quantity>12</quantity>
      <addedby>Amir</addedby>
      <date>2017-10-01 12:34:56 </date>
</node>

What is JSON (a lot easier read data interchange format)
{
  "node": {
    "name": "Eggs",
    "quantity": “12",
    "addedby": “Amir”,
    "date": "2017-10-01 12:34:56"
  }
}

JSON can contain:
    Arrays [1, 2, 3, 4]
    Objects {"key": "value"} (Dictionary, NSDictionary)
    Numbers 1, 3.3
    Strings "anything"


NSURLRequest encapsulates an HTTP method (it contains the URL to send the request to, the HTTP method, and the body of the request), NSURLSession and NSURLSessionTask send HTTP requests

The server response is returned by a session task as an NSData object. 
We then have to parse that using NSJSONSerialization.


Threading

Networking in iOS
Latency of networking requests depends on many factors. There is no way to know for sure when you’ll be done
Don’t perform networking operations on the main thread, meaning don’t update the UI from a background thread
When you start different requests, you can’t know the order in which they finish

Below is the example of the nested databases for the people in a room in both XML and JSON

<people>
	<n>
		<a>
			<person>
				<name>nathan</name>
				<t_color>gray</t_color>
			</person>
		</a>
		….
		<o>
			<person>
				<name>noah</name>
				<t_color>red</t_color>
			</person>
		</o>

	</n>
	<person>
		<name>jamie</name>
		<t_color>black</t_color>
	</person>
	<person>
		<name>kit</name>
		<t_color>dark_gray</t_color>
	</person>
	<person>
		<name>bennet</name>
		<t_color>green</t_color>
	</person>
	<person>
		<name>amir</name>
		<t_color>cyan</t_color>
	</person>
</people>


This is the specific cluster where my user lives
-> People -> a -> m -> i -> r (amir.




JSON


people: 
{
	person: 
		[
			name: amir
			t_color: cyan
		]
	person: 
		[
			name: bennet
			t_color: green
		]
	n:
		[
			a:
				{
					person:
							[
								name: nathan
								t_color: gray
							]
					person:
							[
								name: nana
								t_color: blue
							]
				}
		]
	person: 
		[
			name: john
			t_color: transparent
		]
}



This is the link to the video we spoke of:

Beware online "filter bubbles" | Eli Pariser / Content Catering 
https://www.youtube.com/watch?v=B8ofWFx525s


Our word cloud is also in here:   ![alt text](https://github.com/AmirJahan/LHL---W03-D04/blob/master/Keywords%20W03-d04.png)

