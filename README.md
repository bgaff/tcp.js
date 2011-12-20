TCP.js
======
TCP.js is a library developed during the LinkedIn intern hackday 2011. It will proxy TCP connections using NodeJS and Socket.IO. TCP.js was the foundation of the VNC.js project, read more about them both: http://engineering.linkedin.com/javascript/vncjs-how-build-javascript-vnc-client-24-hour-hackday


Sample Code
-------
var host = "127.0.0.1";
var port = 5900;

var sock = new TCPClient(host,port);

sock.on("connected", function() {
  log("connected to " + host + ":" + port);
  sock.send("Hello from a browser!");
});

sock.on("closed", function() {
  log("The connection has closed :(");
});

sock.on("data", function(msg){
  log("data arrived: " + msg);
});

sock.connect();

Disclaimer
----------
This project was developed over 24 sleep deprived hours, the code is messy and undocumented.
