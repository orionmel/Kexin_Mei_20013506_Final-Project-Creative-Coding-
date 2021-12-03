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
  
This rhino is old and walks on a fixed route every day, it was locked in this pink fence, and do not have enough strength to walk out of this solid fence. A corner of this originally prosperous zoo still retains its previous Wooden sign and sculptures, but the warning "please take care of them, or you will be bitten" has become a decoration, and no one will step into this land anymore. When there was a heavy snowfall in the sky, it was no longer known how long it had passed, and this place became the only place on the earth with a breath of life.

The description of my code :
-------------------------------
### 一、About my 'background sound' ：
1. In the background music, i use the maxiSample from object the Maximilian library ,and mixes two 'sound1.wav' and 'sound2.wav' sound files to play.

```javascript
 audio.init(); 
 audio.loadSample('sound2.wav',mySample);
 audio.loadSample('sound1.wav',mybeat);
```

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

***3. About walking rhinos***    
For walking rhinos, I mainly use curve components, which are characterized by the different curves drawn and the location of the curves, and then make the object move along the curve, thus achieving a good effect of the rhino's movement.  
https://github.com/protyze/aframe-curve-component

The first is the need to import curve component elements  

```javascript
  <script src="https://rawgit.com/aframevr/aframe/master/dist/aframe-master.min.js"></script>
  <script src="https://unpkg.com/aframe-curve-component/dist/aframe-curve-component.min.js"></script>
```

Then draw the curve and the curve point, and then give the drawn curve to the object  

```javascript
 <a-curve id="track1">
       <a-curve-point position="-18 1 -5"></a-curve-point>
       <a-curve-point position="-25 1 -15"></a-curve-point>
       <a-curve-point position="-24 1 -24"></a-curve-point>
       <a-curve-point position="-16 0 -26"></a-curve-point>
       <a-curve-point position="-5 1 -28"></a-curve-point>
       <a-curve-point position="-2 1 -18"></a-curve-point>
       <a-curve-point position="-1 1 -4"></a-curve-point>
       <a-curve-point position="-18 1 -5"></a-curve-point>
</a-curve>
      
       <a-gltf-model class="homeworld" position="-18 1 -9" rotation="0 180 0" scale="2 2 2" src="#rhino"  alongpath="curve: #track1; loop:true; dur:25000; triggers: #point1; rotate: true;" animation-mixer="clip: Armature|walk; duration: 4"></a-gltf-model>
    
```

***4. Other objects imported***   
In order to enrich my environment, I also imported different models, which I think is a good choice  
[1] A pool in a zoo   
```javascript
  <a-asset-item id="pond" src="https://cdn.glitch.com/a33027c6-455e-4408-9565-fbf6fcae10c0%2Fout (7).glb?v=1585263357622" response-type="arraybuffer"></a-asset-item>
```
[2] The fence  
```javascript
  <a-asset-item id="wall" src="https://cdn.glitch.com/a33027c6-455e-4408-9565-fbf6fcae10c0%2Ffence.glb?v=1585209639560" response-type="arraybuffer"></a-asset-item>
```
[3] The rhinos  
```javascript
  <a-asset-item id="rhino" src="https://cdn.glitch.com/a33027c6-455e-4408-9565-fbf6fcae10c0%2Fout (5).glb?v=1584993963933" response-type="arraybuffer"></a-asset-item>
```
[4] The big eyes sculpture
```javascript
  <a-gltf-model
  position="-10 4 8"
  rotation="0 200 0"
  scale=" 0.5 0.5"
  src="https://cdn.glitch.me/41f80828-2b8e-4843-9ec0-a381df334026%2Fout.glb?v=1635521638264"
  ></a-gltf-model>
  <a-box position="-10 -0.5 8" scale="2.5 4 2.5" color="#552b00"></a-box>
```
Difficulties and improvement
-----------------------------
1. The hardest part of the whole project design process was the position of the object and the camera's perspective, because my design angle was to tell the user the information in the fence from a sign outside the fence, so it all took me a lot of time to set a camera angle and then different objects needed to adjust the position and direction according to that angle.  
 
2. About the snow day plug-in, I can not find a very suitable particle dynamics at first, tried many times also did not succeed in the snow day plug-in configuration, and then looked at some information to know is my a-frame version of the reason.    

3. For the special effects of lighting, I do not feel that the picture is enough, I think later try to be able to light track the motion of objects to achieve more interesting effects.
    
4. In my later study of a-frame, I found that a-frame can also implement a lot of ui interface and mouse click to switch different html screen, I think this is another aspect that I can further develop my project, I think in the future I can add some gesture switching interaction, or can use vr glasses to complete a more interesting scene switch.

Reference
===========
[1] [https://aframe.io/docs/1.2.0/primitives/a-sound.html](https://aframe.io/docs/1.2.0/primitives/a-sound.html)

[2] [https://github.com/ual-cci/accellerate-immersive-framework/wiki](https://github.com/ual-cci/accellerate-immersive-framework/wiki)

[3] [https://github.com/supermedium/aframe-environment-component](https://github.com/supermedium/aframe-environment-component)

[4] [https://github.com/IdeaSpaceVR/aframe-particle-system-component](https://github.com/IdeaSpaceVR/aframe-particle-system-component)

[5] [https://github.com/protyze/aframe-curve-component](https://github.com/protyze/aframe-curve-component)

[6] [https://www.youtube.com/watch?v=liOLtcPmMa0&list=PL8MkBHej75fJD-HveDzm4xKrciC5VfYuV&index=4](https://www.youtube.com/watch?v=liOLtcPmMa0&list=PL8MkBHej75fJD-HveDzm4xKrciC5VfYuV&index=4)

[7] [https://aframe.io/aframe-school/#/8](https://aframe.io/aframe-school/#/8)

[8] [https://maxilib-reference.github.io/MaxiLib-Reference/#maxiosc](https://maxilib-reference.github.io/MaxiLib-Reference/#maxiosc)
