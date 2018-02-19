# CS4331 -Virtual_Reality4331 Project1

## Build Your Own House


Demo link :arrow_forward: https://carolynwu.github.io/virtual_reality4331/      
Video :point_right: :point_right: https://www.youtube.com/watch?v=y7DYMudcT2c&feature=youtu.be  :point_left: :point_left:

## Features:
:key: Language:  a-frame:heavy_plus_sign: three.js :heavy_plus_sign: JavaScript  
:key: add models using 
```
<a-assets>
        <a-asset-item id="id" src="src/src/scene.gltf"></a-asset-item>
</a-assets>  

<a-entity gltf-model="a_entity/model/scene.gltf" position="0 0 0" rotation="0 0 0" scale="0 0 0"></a-entity>
```

:zap:SKY
![2018-02-17_21-02-47](https://user-images.githubusercontent.com/22507322/36347805-8406d1f2-1426-11e8-88fe-6f5ea17db593.gif)
```
  <script>
  AFRAME.registerComponent('sun-position-setter', {
          init: function () {
            var skyEl = this.el;
            var orbitEl = this.el.sceneEl.querySelector('#orbit');
            orbitEl.addEventListener('componentchanged', function changeSun (evt) {
                var sunPosition;
                var phi;
                var theta;

                if (evt.detail.name !== 'rotation') { return; }

                sunPosition = orbitEl.getAttribute('rotation');

                if(sunPosition === null) { return; }

                theta = Math.PI * (- 0.5);
                phi = 2 * Math.PI * (sunPosition.y / 360 - 0.5);
                //Debugging position
                //console.log(Math.cos(phi), Math.sin(phi) * Math.sin(theta))
                skyEl.setAttribute('material', 'sunPosition', {
                    x: Math.cos(phi),
                    y: Math.sin(phi) * Math.sin(theta),
                    z: -1
                });
            });
        }
    });
</script>
```

:zap: after clicking the ball can move   
![2018-02-17_21-17-07](https://user-images.githubusercontent.com/22507322/36347857-12c563b2-1428-11e8-96f0-e723544382e8.gif)  
```
 <a-animation attribute="position" from="10.636 1.063 -12.74" to="10.636 5.609 -12.74" dur="2000" direction="alternate" repeat="indefinite" begin="click" ></a-animation>
```
use ```begin="click"``` and it will interact with cursor  
Reference :arrow_forward: https://www.youtube.com/watch?v=SyU9dEt7tNs

:zap: switch the light  
![2018-02-18_14-22-41](https://user-images.githubusercontent.com/22507322/36356399-3e21b9d6-14b7-11e8-88b2-8afb8178e93f.gif)
use javascript to change the color from grey to white.
```
 <script>
        function setLight(){
            var light = document.querySelector('#main-light');
            var current_color = light.getAttribute('color');
            if (current_color == 'grey'){
                light.setAttribute('color', 'white');
            }
            else{
                light.setAttribute('color', 'grey');
            }
        }
    </script>
```

:zap:  trigged dog's sound

```
 <a-entity gltf-model="#dog" position="-8.06 -0.09 11.41" rotation="0 180 0"  scale="0.02 0.02 0.02"></a-entity>
 <a-box material="color:tomato;transparent:true;opacity:0" depth="2" height="2" width="2" sound="src: url(images/dog_sound.mp3); on: click" class="intersectable" position="-8.06 -0.117 11.41"></a-box>
```

:zap: background music  
Reference  :arrow_forward:  https://github.com/etiennepinchon/aframe-resonance

## **Grading:**  
For a C, you need to:
* ~~Customize the TTU Computer Science VR showroom into your dream house with your own style of floor and ceiling~~
* ~~Have at least unique 10 models at appropriate locations~~
* ~~Have appropriate lighting. Do not give me a dark screen.~~

For a B, you need to:
* ~~Add an additional 5 unique models~~
* ~~Give the user control over the lighting~~
* ~~You should be able to navigate around the space~~

For a A, you need to:
* ~~Interact with certain objects: Click to trigger a sound track or a song, or
Add one dynamic object (moving model, such as a dog or an avatar)~~


## **External Model Sources**
### **in front of the house**
:one: house plate  
:two: dog  https://sketchfab.com/models/dadb71216dbc4dcfbdd8baee9bdf3ce00 
dog sound: https://www.zapsplat.com/sound-effect-category/dogs/
![in_front_of_door](https://user-images.githubusercontent.com/22507322/36346696-ee6e9a20-1408-11e8-9316-86404e9e804e.PNG)

### **living room**
:one: TV    
:two: TV cabinet    
:three: kitchen cabinet   
:four: counter top   
:five: table 
:six: swith  
:seven: sofa  
:eight: coffee table  https://sketchfab.com/models/475cfd550f3648178efdf98152a4bc390  
:nine: chair https://sketchfab.com/models/d2785b57e7da45858f2fe8bf4dedd68d     
:one: :zero: tv remote https://sketchfab.com/models/67a5956349574fac8431b9b12aad8b81    
:one: :one: bottle https://sketchfab.com/models/833ef9cea519454fb1d249154b830f04    
backgorund music: http://freemusicarchive.org/music/Kevin_MacLeod/Classical_Sampler/Canon_in_D_Major

![living room](https://user-images.githubusercontent.com/22507322/36346795-e4d8e120-140b-11e8-986d-cdaab7afc6aa.PNG)


### **bedroom**
:one: bed  https://sketchfab.com/models/86d5c8b1addf4f138d8f0c2cf06e9ba0 
![bed](https://user-images.githubusercontent.com/22507322/36346802-0f9d1bb0-140c-11e8-886a-7020fbdf355e.PNG)


### **outdoor**
:one: swimming pool  
:two: basketball   
:three: swing  https://sketchfab.com/models/da0fe69537504073badaa3c44db50030   
:four: umbrella  https://sketchfab.com/models/e0c0ad33836d488da98ba8c4f807b1fe      
:five: basketball hoop  https://sketchfab.com/models/b882a4fd9e554e76924f55eac40d69c8 
![outdoor](https://user-images.githubusercontent.com/22507322/36346805-2228bd98-140c-11e8-8de7-82903389292e.PNG)



