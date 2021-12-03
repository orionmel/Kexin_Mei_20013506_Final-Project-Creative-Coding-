# Kexin_Mei_Final Artwork- Advanced Creative Computing
***
My Github Link :
----------------------
https://github.com/orionmel/Kexin_Mei_20013506_Final-Project-Creative-Coding-

My Mimic Link :
----------------------
https://mimicproject.com/code/6cf236c6-8055-1c55-7577-ae395d51bcd1

My Video Link :
-------------------
https://vimeo.com/manage/videos/652481884

***
The Only Rhino On The Earth
=============================
### Background :
In the future, as humans continue to get resources from the earth, and the earth gradually become barren, then the usable and survivable area become smaller and smaller. Therefore, in order to survive better, humans escape the earth and choose to live on other planets. They take away all the things that belonged to'them' and left this once beautiful home without looking back, but they left a rhino in the zoo.  
  
This rhino is old and walks on a fixed route every day, it was locked in this pink fence, and do not have enough strength to walk out of this solid fence. A corner of this originally prosperous zoo still retains its previous Wooden sign and sculptures, but the warning "please take care of them, or you will get hurt" has become a decoration, and no one will step into this land anymore. When there was a heavy snowfall in the sky, it was no longer known how long it had passed, and this place became the only place on the earth with a breath of life.

The description of my code :
-------------------------------
### 一、About my 'background sound' ：
1. In the background music, i use the maxiSample from object the Maximilian library ,and mixes two 'sound1.wav' and 'sound2.wav' sound files to play.
2. I also used the maxiClock system, in order to create a bit of rhythm, I used two audio files playHead at a specific point in time, and then let the audio play more interesting, and each sample only play once.

### 二、About a-frame visualization scenes ：
***1. About  visualization scene***  
I started with an environment plug-in that allowed different modes to be selected, and the 'dream' mode was used after a comprehensive consideration.  
https://github.com/supermedium/aframe-environment-component

Use this plug-in, you first need to import resources  

```javascript
<script src="https://unpkg.com/aframe-environment-component@1.2.0/dist/aframe-environment-component.min.js"></script>
```
Then, extract the plug-in resources to create an object and use it  

```javascript
<a-entity environment="preset: dream" shadow="receive: true"></a-entity>
```
***2.About the snow effect***    
https://github.com/IdeaSpaceVR/aframe-particle-system-component  
I used a snow plug-in, which is more convenient to use, but after my experiment, need to have a-frame system requirements, only support the older version of 1.0.4

```javascript
<script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>
```
Using this plug-in also requires the import of two elements first  

```javascript
<script src="https://rawgit.com/takahirox/aframe-rain/master/build/aframe-rain.min.js"></script>
<script src="https://unpkg.com/aframe-particle-system-component@1.0.x/dist/aframe-particle-system-component.min.js"></script>
```

Then insert the rain object extracted by the plug-in in the middle of the < a-scene > </a-scene >, and you can adjust the size, color, etc. of the snowflakes and the shape reflected on the ground 

```javascript
<a-scene
                 background="color: #8098cf"
               fog="type: linear; color: #000000"
                  rain="count:20000;
                   dropHeight: .15;
                   dropRadius: .15;
                   height: 1000;
                   color: white;
                   splash: false"
              >
```  

