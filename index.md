<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Home</title>
    <script src="https://code.jquery.com/jquery-3.3.1.js" integrity="sha256-2Kok7MbOyxpgUVvAk/HJ2jigOSYS2auK4Pfzbm7uH60=" crossorigin="anonymous"></script>

</head>
<body>
    <div class="Main_head"
        <h1 id="Main_head">LIGHTS  </h1>
    </div>
    <div class="Control_Section">
        <h2>Lights Control</h2>
        <div class="button">
            <span>
                    <!-- https://api.thingspeak.com/update?api_key=FUEVXY43JRV45FHR&field1=0 -->
                <button id="ON" onclick="onState('FUEVXY43JRV45FHR', 1, 1)">ON</button> <!-- api, field Number, value -->
                <button id="OFF" onclick="offState('FUEVXY43JRV45FHR', 1, 0)">OFF</button> <!-- api, field Number, value -->
                <script>
                    function onState(api, field, value) {
                        $.post('https://api.thingspeak.com/update?api_key=' + api + '&field' + field + '=' + value);
                        console.log("HIGH"); 
                        alert("wait 15 secs");
                    }

                    function offState(api, field, value) {
                        $.post('https://api.thingspeak.com/update?api_key=' + api + '&field' + field + '=' + value);
                        console.log("LOW");alert("wait 15 secs");
                        
                    }
                    function disabler(){
                        var btns=document.getElementsByClassName("button");


                    }
                    function readState(){
                        var status;
                        // https://api.thingspeak.com/channels/266256/fields/2/last.json
                    $.getJSON("https://api.thingspeak.com/channels/832714/fields/1/last.json?api_key=I4HQ6KLWWLUNZWCJ",function(data){
                        if(data.field1==1){status = "are on"}else{status = "are off";}
                        document.getElementById("Main_head").innerHTML="lights "+status
                        console.log(data.field1);
                    });
                    }
                    setInterval(readState,2000);
                </script>
            </span>
        </div>
    </div>
    <script src="https://gist.github.com/Rayanfer32/224ef2dd05eb7170d8d9ad9687d01653.js"></script>
</body>

<style>
        @import url('https://fonts.googleapis.com/css?family=Roboto+Slab');
        @import url('https://fonts.googleapis.com/css?family=Viga');
body {
	height: 100%;
	margin: 0;
	padding: 0;
	font-family: Roboto Slab, Viga, sans-serif;
	background-image: linear-gradient(to right, #319301 , #aa52c5); 
	background-attachment: fixed;
}
	
.Main_head {
	position: relative;
	text-align: center;
	margin-top: 50px;
	font-size: 50px;
	color:#ffffff;
	font-weight: 600;
	letter-spacing: 1vh;
}

.Control_Section {
	z-index: -1;
	background-color: #dbdbdb79;
	margin: 10%;
	margin-top: 20px;
	border: 10px ;
  	padding: 10px;
	box-shadow: 5px 0px 100px 0px #dfdfdf79;
	color: #ffffff;
	border-radius: 100px;
}

.Control_Section h2 {
	margin: auto;
	text-align: center;
  	width: 100%;
	padding: 20px;
	letter-spacing: 2px;
	font-weight: bold;
}

span {
	display: inline;
}

.button{
	z-index: 1;
	text-align: center;
	opacity: 100px;
}

#ON {
	padding: 20px 20px;
	margin: 40px;
	background-color: #1eb40079;
	color: #ffffff;
	cursor: pointer;
	font-family: Viga;
	font-size: 40px;	
	border: 5px solid #1eb40079;
	transition: 0.5s;
	border-radius: 100px;
}

#OFF {
	padding: 20px 20px;
	margin: 30px;
	background-color: #b4000079;
	color: #ffffff;
	cursor: pointer;
	font-family: Viga;	
	font-size: 40px;
	border: 5px solid #b4000079;
	transition: 0.5s;
	border-radius: 100px;
}

#ON:hover {
	color: #1eb400;
	background-color: #dfffe7;
}

#OFF:hover {
	color: #b40000;
	background-color: #ffecec;
}


div #alert {
	display: none;
	z-index: 1;
	text-align: center;
	font-size: 30px;
	font-weight: bold;
}

#time {
	font-size: 50px;
	font-weight: bold;
	letter-spacing: 10px;
	color: red;
}
    </style>

</html>
## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Rayanfer32/cloud/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Rayanfer32/cloud/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
