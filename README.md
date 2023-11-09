<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JoyVista Webtop</title>
    <script>
        function updateClock() {
            var now = new Date();
            var hours = now.getHours();
            var minutes = now.getMinutes();
            var ampm = hours >= 12 ? 'PM' : 'AM';

            hours = hours % 12;
            hours = hours ? hours : 12; // Handle midnight (0 hours)

            minutes = minutes < 10 ? '0' + minutes : minutes;

            var timeString = hours + ':' + minutes + ' ' + ampm;

            document.getElementById('digital-clock').innerText = timeString;
        }

        // Update the clock every second
        setInterval(updateClock, 1000);

        // Initial call to display the clock immediately
        updateClock();
    </script>
	<script>
		var show = False;
		var background = 'https://i.ibb.co/jLfbVcH/webtop.png'; // Default background
		
	    function storeInput() {
		var background = document.getElementById('user-input').value;
		console.log('Stored background value:', background);
	        document.body.style.backgroundImage = `url('${background}')`;
		// You can use the 'background' variable for further processing or storage
	    }
	    function rickground() {
	    	var background = "https://static.wikia.nocookie.net/the-know-your-meme-archive/images/6/6c/Rickroll.jpg/revision/latest?cb=20201005232811";
	    	console.log('Get rickrolled you fat fuck');
	    	document.body.style.backgroundImage = `url('${background}')`;
	    }
	    function fetcch() {
		fetch('https://inspirobot.me/api?generate=true')
		    .then(response => response.text())
		    .then(imageUrl => document.getElementById('inspirobot-image').src = imageUrl);
	    }
	    function showSettings() {
	        var settingsWindow = document.getElementById('settings-window');
	        show = !show;  // Toggle the value
	        if (show) {
		    settingsWindow.style.display = 'block';
	        } else {
		    settingsWindow.style.display = 'none';
	        }
	    }

	</script>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-image: url(background);
            background-size: 1920px 1080px;
            background-position: center;
            background-repeat: no-repeat;
            height: 100vh;
            overflow: hidden;
        }

        #desktop {
            padding: 20px;
        }

	#quote-widget {
		position: absolute;
	        top: 0;
        	right: 0;
    	}
    	
        .desktop-icon img {
        	width: 40px; /* Adjust the width as needed */
        	height: auto;
    	}

        #taskbar {
            background-color: #333;
            color: #fff;
            padding: 10px;
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            text-align: center;
        }
        .settings-window {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 300px;
            height: 200px;
            background-color: #808080; /* Grey color */
            border: 1px solid #000;
            z-index: 1;
            display: none;
        }
    </style>
</head>
<body>
    <div id="desktop">
	    <div class="desktop-icon" onclick="rickground()">
		<img src="https://cdn-icons-png.flaticon.com/512/3606/3606645.png" alt="Icon 1">
		<span></span>
	    </div>
	    <br>
        <div class="desktop-icon" id="settings-icon" onclick="showSettings()">
            <img src="https://cdn-icons-png.flaticon.com/512/771/771203.png" alt="Settings" width="40" height="40">
            <span></span>
        </div>
        <br>
	    <a href="https://eaglercraft.com/mc/b1.3" target="_blank">
		<img src="https://static.wikia.nocookie.net/animatorvsanimation/images/5/52/MinecraftIcon.png/revision/latest/thumbnail/width/360/height/360?cb=20190830150033" alt="Minecraft" width="40" height="40">
	    </a>
	    <br>
	    <a href="https://chat.openai.com" target="_blank">
		<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/04/ChatGPT_logo.svg/1200px-ChatGPT_logo.svg.png" alt="ChatGPT" width="40" height="40">
	    </a>
	    <br>
	    <a href="https://reddit.com" target="_blank">
		<img src="https://pbs.twimg.com/profile_images/1684669052839473152/e_ATYqfK_400x400.jpg" alt="Reddit" width="40" height="40">
	    </a>
	    <br>
	    <a href="https://hackaday.com" target="_blank">
		<img src="https://www.svgrepo.com/show/306167/hackaday.svg" alt="Hackaday" width="40" height="40">
	    </a>
	    <br>
	    <a href="https://gmail.com" target="_blank">
		<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Gmail_Icon_%282013-2020%29.svg/2560px-Gmail_Icon_%282013-2020%29.svg.png" alt="Gmail" width="40" height="40">
	    </a>
	    <div class="settings-window" id="settings-window">
			<input type="radio" id="LM" name="light mode" value="Light Mode" onclick="document.getElementById('DM').checked = false; document.getElementById('taskbar').style.backgroundColor = '#aaa';
">
			<label for="light mode">Light Mode</label><br>
			<input type="radio" id="DM" name="dark mode" value="Dark Mode" onclick="document.getElementById('LM').checked = false; document.getElementById('taskbar').style.backgroundColor = '#333';">
			<label for="dark mode">Dark Mode</label><br>
			Background:
		        <input type="text" id="user-input" name="user-input" placeholder="Type something..." value="https://raw.githubusercontent.com/dorianpro/kaliwallpapers/master/kali-linux-wallpaper-v2.png">
		        <button type="button" onclick="storeInput()">Submit</button>
		        <br> taskbar positioning: <br>
		        <input type="radio" id="LTSKB" name="LTSKB" value="LTSKB" onclick="document.getElementById('CTSKB').checked = false; document.getElementById('RTSKB').checked = false; document.getElementById('taskbar').style.textAlign = 'left';
">
			<label for="LTSKB">Left</label><br>
		        <input type="radio" id="CTSKB" name="CTSKB" value="CTSKB" onclick="document.getElementById('RTSKB').checked = false; document.getElementById('LTSKB').checked = false; document.getElementById('taskbar').style.textAlign = 'center';
">
			<label for="CTSKB">Center</label><br>
		        <input type="radio" id="RTSKB" name="RTSKB" value="RTSKB" onclick="document.getElementById('LTSKB').checked = false; document.getElementById('CTSKB').checked = false; document.getElementById('taskbar').style.textAlign = 'right';
">
			<label for="RTSKB">Right</label><br>
		</div>

	<div id="quote-widget">
        <a href="javascript:void(0);" onclick="fetcch()">
            <img id="inspirobot-image" src="https://generated.inspirobot.me/a/paejqkQB6v.jpg" width="300" height="200">
        </a>
	    <script>
		// Fetch image URL from InspiroBot API
		fetcch()
	    </script>
       <div id="input-icon">
            <form id="input-form">
            </form>
        </div>
	</div>
	<div id="taskbar">
	    <a href="https://www.youtube.com/" target="_blank">
		<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/YouTube_icon_%282013-2017%29.svg/1200px-YouTube_icon_%282013-2017%29.svg.png" alt="YouTube" width="30" height="30">
	    </a>
	    <a href="https://onlinenotepad.org/notepad" target="_blank">
		<img src="https://play-lh.googleusercontent.com/jD8waDJPN1yv4OdcB6_ILw9M4kyNPdtgBYtoTiPrYhxA1l4FLSKXXe4kAcDCjmtZmQ4" alt="Notepad" width="30" height="30">
	    </a>
	    <a href="https://wikipedia.org" target="_blank">
		<img src="https://upload.wikimedia.org/wikipedia/en/thumb/8/80/Wikipedia-logo-v2.svg/1200px-Wikipedia-logo-v2.svg.png" alt="Wikipedia" width="30" height="30">
	    </a>
	    <div id="digital-clock">12:00 AM</div>
	</div>
    </div>
    <script>
		background="https://i.ibb.co/jLfbVcH/webtop.png"
	    document.getElementById('user-input').value = background;
	    storeInput();
	    document.getElementById('DM').checked = true;
	    document.getElementById('CTSKB').checked = true;
	</script>
</body>
</html>

