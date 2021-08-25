## dashboard-container

#### install http-server global

`$npm i -g http-server`

##### start the server and bind the port to page.html

##### start applicationA on a seperate terminal

`http-server -p 8080 ./public`

##### start applicationB on a seperate terminal

`http-server -p 5000 ./public`

##### browse to 

`http://localhost:8080`

`http://localhost:5000`

#### References:

[Window.postMessage](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)

[Cross communication](https://javascript.info/cross-window-communication)

 
**Note:**
 - Need to add instructions for other os environments (windows).
 - Anyone interested in adding the above documentation is most welcomed!
 - [Posting JSON object to iFrame](https://www.py4u.net/discuss/1202629)
 
   html
   ```
   <button onclick="_sendMessage ()">Send</button>
   <iframe src="" id="myIframe"
   ```
 
   javascript
   ```
   var myIframe = document.getElementById('myIframe');
   myIframe.contentWindow.addEventListener('message', function(event) {
      console.log(JSON.parse(event.data));
   }, false);
   
   
   window._sendMessage = function() {
      var json = {payload:'Hello World'};
      myIframe.contentWindow.postMessage(JSON.stringify(json), '*');
   }
   ```
   
