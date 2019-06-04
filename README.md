# Design system Development

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# Vaststellen van patronen

We beginnen met de discussie "wat moet er op een pagina komen". Die komt in een Google Spreadsheet. Hierin wordt, samen met de klant, welke pagina's er moeten komen, en wat er op die pagina's getoond moet worden. Dit kan al samen met het maken van de eerste schetsen.

### Site structuur en Wireframes:
  - Google sheets (voor site structuur)
  - Freehand (Voor wireframes)

#### Sitestructuur
Bij een groter project houdt het bepalen van de gewenste content in:
- Overleggen met klant;
- Uitzoeken concurrenten; 
- Wat is de huidige structuur? 
- Bepalen in een story board welke content en functies er nodig zijn.
- Bepalen in een sitemap welke pagina's, welke content nodig hebben.
- Sitemap en Storyboard moeten op een bepaalde manier aan elkaar gekoppeld zijn.
- Storyboard kan erg helpen bij het bepalen welke functionaliteiten er gebouwd moeten worden, kan lastiger zijn om overzicht te bewaren..

Door vaker te werken met de story boards kunnen die ook meer standaard worden waardoor we mogelijk sneller met componenten kunnen gaan werken. Als het patroon vaker hetzelfde is, is er makkelijker op te varieren.  

#### Wireframes
We beginnen met mobiele schetsen van de belangrijkste pagina's. Door de beperkingen van het kleine scherm, kunnen we gelijk zien of we de juiste informatie op het scherm hebben en of het in de juiste volgorde hebben staan.

Vanuit hier kan worden bepaald welke content patronen er ontstaan, maar ook welke UI patronen er zijn. 

# Vaststellen van de Visuele richting

>Historically, visual designers have gone about this by creating full comps—often many comps—to feel out the aesthetic >values of the organization. Throw some comps against the wall and see what sticks. As you might imagine, generating a >slew of comps from scratch takes an immense amount of time and effort, and unfortunately much of that work finds itself >on the cutting room floor. There must be a more efficient way.

### The 20-second gut test

Gebruikt: Google slides.

We gaan op zoek naar 20 verschillende websites liefst in de branche van de klant. Elk van deze websites wordt 20 seconden getoond. 
Klant geeft van elk getoond scherm een score van 1 tot 10. Daarbij ook in 1 woord het gevoel dat het oproept. Bij uitgebreidere sites, zijn we hierbij aanwezig om te discussieren en om te notuleren. Bij kleinere sites, kunnen we dit op afstand doen. 
Ten minste met het team bespreken: 5 hoogste scores, 5 laagste scores.

### "huisstijl"
Gebruik: 
- Design System Management (DSM)
- Freehand

In de DSM, (of een Board in inVision), een scherm maken met de kleuren en de teksten waaraan we aan het denken zijn, op basis van de "gut test" en de Mobiele wire frames. In een later stadium wordt dit uitgebreid met de componenten. 

Voor het beste overzicht staan nu de teksten en kleuren in DSM, de basis componenten staan hier ook al in? Het "gevoel" van hoe de mobiele homepage eruit ziet, staat nu in de Freehand. 

Losse componenten kunnen nu worden vormgegeven en worden gepubliceerd in DSM, freehand of en Board. Die laatste moeten we nog verder onderzoeken omdat die nog niet in de workflow zit op dit moment. 


# Front end "preppen"
Als de componenten door de backend developer in de test site gezet zijn, kunnen de componenten die goedgekeurd zijn door de klant per stuk worden vormgegeven door de front end developer.

# Vaststellen en produceren content!

Het is binnen (grote) webprojecten vaak ingewikkeld voor klanten, tekstschrijvers en marketeers, lastig om te bepalen welke content ze moeten produceren. Door Gebruik te maken van schetsen en componenten kunnen we makkelijker communiceren over waar welke content moet komen en hoe lang die ongeveer mag zijn. 



### Tech

Dillinger uses a number of open source projects to work properly:

* [AngularJS] - HTML enhanced for web apps!
* [Ace Editor] - awesome web-based text editor
* [markdown-it] - Markdown parser done right. Fast and easy to extend.
* [Twitter Bootstrap] - great UI boilerplate for modern web apps
* [node.js] - evented I/O for the backend
* [Express] - fast node.js network app framework [@tjholowaychuk]
* [Gulp] - the streaming build system
* [Breakdance](http://breakdance.io) - HTML to Markdown converter
* [jQuery] - duh

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

### Installation

Dillinger requires [Node.js](https://nodejs.org/) v4+ to run.

Install the dependencies and devDependencies and start the server.

```sh
$ cd dillinger
$ npm install -d
$ node app
```

For production environments...

```sh
$ npm install --production
$ NODE_ENV=production node app
```

### Plugins

Dillinger is currently extended with the following plugins. Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| Github | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |


### Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantanously see your updates!

Open your favorite Terminal and run these commands.

First Tab:
```sh
$ node app
```

Second Tab:
```sh
$ gulp watch
```

(optional) Third:
```sh
$ karma test
```
#### Building for source
For production release:
```sh
$ gulp build --prod
```
Generating pre-built zip archives for distribution:
```sh
$ gulp build dist --prod
```
### Docker
Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the Dockerfile if necessary. When ready, simply use the Dockerfile to build the image.

```sh
cd dillinger
docker build -t joemccann/dillinger:${package.json.version} .
```
This will create the dillinger image and pull in the necessary dependencies. Be sure to swap out `${package.json.version}` with the actual version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on your host. In this example, we simply map port 8000 of the host to port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart="always" <youruser>/dillinger:${package.json.version}
```

Verify the deployment by navigating to your server address in your preferred browser.

```sh
127.0.0.1:8000
```

#### Kubernetes + Google Cloud

See [KUBERNETES.md](https://github.com/joemccann/dillinger/blob/master/KUBERNETES.md)


### Todos

 - Write MORE Tests
 - Add Night Mode

License
----

MIT


**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>

