# MuseEEG-FireBase and Web 

Sending `Electroencephalography`(EEG) data to a webpage via Firebase real time database using Muse EEG headset

This is an example built on the muse Android sdk example code modified to communicate EEG data to a webpage. 
It contains Firebase hooks in the android app and analogus hooks on the webpage.

## Installation
1. [create A Firbase account](https://firebase.google.com/?gclid=EAIaIQobChMIqozErZLT2AIVwYuzCh2pzwM4EAAYASAAEgK0s_D_BwE)


### Connect Android Troject To Firebase
For the code to run you need to add a Firebase backend for the code to connect to.

2.	Open the android code and add firbase backend to the project and name the Firebase Project what you want.
Click tools -Firebase->Realtime Database- save and retrieve data

	![record screenshot](img/fbsetup3.png)
	
	
If this does not work you could try this video.
(https://www.youtube.com/watch?v=YVu_xSzn2u0)

	
### Connect Webpage To Firebase
3.	Open the html file in the `JeanWebmuse-webView` folder and add the link from firebase to the correct section.

```javascript
<script src="https://www.gstatic.com/firebasejs/4.8.2/firebase.js"></script>
<script>
  // Initialize Firebase
  // TODO: Replace with your project's customized code snippet
  var config = {
    apiKey: "<API_KEY>",
    authDomain: "<PROJECT_ID>.firebaseapp.com",
    databaseURL: "https://<DATABASE_NAME>.firebaseio.com",
    storageBucket: "<BUCKET>.appspot.com",
    messagingSenderId: "<SENDER_ID>",
  };
  firebase.initializeApp(config);
</script>
```

If you have any issues see this link [Add Firebase to your web Project](https://firebase.google.com/docs/web/setup)	
	
### Configure Firebase Project 
4.	Import the Jason `musetest.json` into your the firebase database for this project 

![screenshot](img/fbsetup4.png) ![screenshot](img/fbsetup5.png)

5.set your Rules in Firebase -read and write to true for testing reasons.
```json
{
  "rules": {
    ".read": "true",
    ".write": "true"
  }
}
```

## Running the code
6.	Run the code on your android device
7.	Connect the muse headset to the app
8.	once you start seeing data, run the `fbtest.html` (located in the JeanWebmuse-webView folder) in the browser to see the data from Firebase. This show an example of pulling the data into a web app!
