<p><span style="color: #000000;"><!-- ######## This is a comment, visible only in the source editor  ######## --></span></p>
<h2><span style="color: #000000;">Smartcodehub A full-stack web application generator&nbsp;</span></h2>
<p><span style="color: #000000;"></span></p>
<p><span style="color: #000000;"></span></p>
<p><span style="color: #000000;"><strong>Vision:</strong> Create Application in almost all languages and all combinations like node react, node angular, .net vue ...and so on</span></p>
<p><span style="color: #000000;"></span></p>
<p><span style="color: #000000;">First Lets Clone the backend and frontend Repositories</span></p>
<pre><span style="color: #000000;">git clone https://github.com/Smart-code-hub/Smartcodehub-api</span><br /><span style="color: #000000;">git clone https://github.com/Smart-code-hub/Smartcodehub-Webapp</span></pre>
<p style="color: #4485b8;"><span style="color: #000000;">Once cloned we can create the docker-compose file as follows</span></p>
<pre><span style="color: #000000;"> 
version: '3'
services:
api:
    container_name: Smartcodehub-api
    restart: always
    build: ./Smartcodehub-api/.
    ports:
    - "3666:3666"
    volumes:
    - .:/app
    links:
    - Smartcodehub-db
    networks:
    - Smartcodehub
app:
    container_name: Smartcodehub-webapp
    restart: always
    build: ./Smartcodehub-webapp/.
    ports:
    - "3667:80"
    volumes:
    - .:/app  
    networks:
    - Smartcodehub       
Smartcodehub-db:
    container_name: Smartcodehub-db
    image: mongo
    ports:
    - "27018:27017"
    networks:
    - Smartcodehub
networks:
Smartcodehub:</span></pre>
<p><span style="color: #000000;">Just the final command</span></p>
<pre><span style="color: #000000;">docker-compose up</span></pre>
