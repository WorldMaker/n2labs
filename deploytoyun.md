# Running a Johnny-Five app on your Yun

Now that you've got a johnny-five app running from your laptop controlling a device, the next thing you can do, if you have a Yun, is deploy to the Yun and let it run the app by itself. 

If you got the Yun from me, it's probably already set up. If you didn't you'll need to install Node and Johnny Five on the Yun by following the directions at [Prepping your Yun for Johnny-Five](preppingyunforjohnnyfiveandnitrogen.md). 

## Deploying to the Yun

1. Get your IP Address for your Yun by following the directions at [IP Address Sketch for your Yun](gettingyouripaddressonayun.md)
2. Prep your yun by following the directions at [Prepping your yun for johnny-five and Nitrogen](./preppingyunforjohnnyfiveandnitrogen.md)
3. Make sure that you've got the StandardFirmata on the Yun. 
4. SSH to your Yun and create a folder 
	a. If you are running Windows, you'll need to install an SSH client. You can use [PuTTY](http://www.putty.org/). If you are using PuTTY then you'll use the visual wizard to connect. 

	`ssh root@<your ip address'

	use the password "arduino" unless you changed it from the default. 

5. Use scp to deploy your files to the Yun
	a. If you are running Windows, you'll need to install an SCP client. You can use [SCP for Windows](http://winscp.net/eng/index.php) or whatever SCP client you like. 

	`scp root@<yun ip address>:blinkn2.js /code/blinkyn2.js`
	`scp root@<yun ip address>:package.json /code/package.json`

	use the password "arduino" unless you changed it from the default. 

6. In your SSH, use NPM to install your dependencies. 

	```
	cd /code/
	npm install 
	```

	This will look at the package.json and install everything that we need. It will likely take a few moments to run. 

7. Now run your node app in the Yun
	
	`node blinkyn2.js`
	
## Summary

At this point your app should be running on your Yun. You can remotely send it an N2 command and turn on and off your light. 