
# Duck Demo

AR experience using Endymion Library to say hello to a duck!



## Features

- Render 3D assets with a simple javascript code


## Getting Started

For run demo you have to perform this step:   

1 - Download with your device (Android) the Endymion Browser apk scanning this qr code and clicking on "Download Beta"        
    (registration is required)   

![Endymion Browser](https://endymion.tech/endymion-address-qrcode-300x300.png)      



2 - Install Docker on your computer, download available here: [Docker Download](https://docs.docker.com/desktop/)

3 - open your computer firewall for 8081 tcp port   
for linux
```bash
    sudo ufw allow 8080
```
for windows using powershell with admin privilege
```powershell
netsh advfirewall firewall add rule name="duomondo-demo" dir=in action=allow protocol=TCP localport=8080
```
    
## Run Locally

Clone the project, go to the project directory, install dependencies and run demo

```bash
git clone https://github.com/EndymionDemo/duck-demo.git  
cd duck-demo    
npm install   
npm run start   

```
Ensure that your smartphone and your computer are connected to same wifi/LAN        
And Finally scan QR Code that appear in terminal with Endymion Browser App and visualize assets


To stop demo    

```bash
  npm run stop
```

## Usage/Examples
In Demo folder there are some files and folders used for experience        
Folders     
1 - assets folder - 3D assets           
2 - audio folder - audio used in animation           
3 - images folder - used images     
4 - js folder - endymion.js library         
5 - style folder - css stylesheet     

Files       
1 - *.arsd - tell to endymion app some stuff that describe scene        
2 - *.html - describe 3D experience with html and using endymion.js library     

Lets explore index.html
```html
<!doctype html>
<html>
<head>
  <title>Duck Demo</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <script src="endymion.js"></script>
  <style>
    .container{
        display: flex;
        justify-content: center;
        align-items: center;
        width:100%;
        height: 100vh;
        position: relative;
    }
    .container .say-hello{
        font-size: 48px;
        text-transform: uppercase;
        background-color: #4472C4;
        color: white;
        padding: 8px 25px;
        border: 2px solid #B4C7E7;
        box-shadow: 0px 0px 4px black;
        cursor: pointer;
        width: 600px;
        height: 200px;
        margin-top:700px;
    }
    .nuvoletta-container{
        width: 400px;
        position: absolute;
        left: 10px;
        top: 30px;

    }
    .nuvoletta-container .nuvoletta{
        width:100%;
        height: auto;
    }

  </style>
</head>
<body>
    <div class="container">
        <button class="say-hello" onclick="sayHello()">say hello!</button>
        <div id="nuvoletta-container" class="nuvoletta-container">
          <img class="nuvoletta" src="assets/Hello.png" />
        </div>
    </div>

    <script>
        var nuvoletta = document.getElementById("nuvoletta-container");
        nuvoletta.style.display = "none";
        let duck = en.asset();
        duck.setPos(0, -0.2, 0)
        .setScale(0.3)
        .load("assets/DUCK.glb");
            

        function sayHello() {
            var nuvoletta = document.getElementById("nuvoletta-container");
            var visible = nuvoletta.style.display;
            if (visible == 'block') {
                nuvoletta.style.display = "none";
            } else {
                nuvoletta.style.display = "block";
            }
        }
    </script>

</body>
</html>

```


## License

[MIT](https://choosealicense.com/licenses/mit/)

