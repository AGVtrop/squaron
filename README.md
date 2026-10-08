# Squaron
If snake had two players.



## how it works
It shrinks a normal html file into the URI only page using a build script. 

## Running:
Paste the dist/uri.txt into your browser's URL bar, or run my version straight from here :D
```
data:text/html,<body><style>*{text-align:center}body{background:black;color:white;font-family:sans-serif}canvas{height:97vh;aspect-ratio:1 / 1}div{text-align:center;padding-top:25%25}</style><h3 hidden id="endText"></h3><div id=startPage><button autofocus id=startButton>Start Game!</button><details style="padding-top: 1%25"><summary>Game info</summary><p>Snake but multiplayer :D</p><hr><p>Player 1: Arrow keys</p><p>Player 2: WASD</p></details></div><canvas id=canvas height=500 width=500 style="border: 2px solid white"></canvas><script>function t(t){return Math.floor(Math.random()*t)}function e(t,e,n,r,o,l,a){const i=[];for(var f=0;f<r;f++)i[f]={x:t,y:e};return{x:Math.floor(t),y:Math.floor(e),v:n,d:0,t:i,c:o,cc:l,m:!1,k:!1,q:a}}function n(t){switch(t.d){case 0:t.y-=1;break;case 1:t.x+=1;break;case 2:t.y+=1;break;case 3:t.x-=1}t.t[0].m=!0,t.t.push(t.t.shift()),t.t[0].m=!1,t.t[0].x=t.x,t.t[0].y=t.y,t.k=!1}function r(t,e){(t.x<0||t.y<0||t.x>f||t.y>f)&&l(`${t.q} hit the wall D:`);for(var n=0;n<e.length;n++)if(e[n].x==t.x&&e[n].y==t.y){for(var r=0;r<5;r++)t.t.push({x:t.x,y:t.y});e.splice(n,1)}for(n=0;n<u.length;n++){var o=u[n];for(r=0;r<o.t.length;r++)1==o.t[r].m&&o.t[r].x==t.x&&o.t[r].y==t.y&&l(`${t.q} got slithered, ${o.q} won`)}}function o(t,e,n){t.fillStyle=e.cc.tail;for(var r=0;r<e.t.length;r++)t.fillRect(e.t[r].x*n,e.t[r].y*n,n,n);t.fillStyle=e.cc.head,t.fillRect(e.x*n,e.y*n,n,n)}function l(t){var e=document.getElementById("endText");e.textContent=`Game Over: ${t}  Ctrl + R to restart`,e.hidden=!1,cancelAnimationFrame(window.requestAnimationFrame())}const a=document.getElementById("canvas"),i=a.getContext("2d");a.hidden=!0,document.getElementById("startButton").addEventListener("click",t=>{document.getElementById("startPage").hidden=!0,a.hidden=!1,requestAnimationFrame(v)}),document.addEventListener("keydown",function(t){for(var e=0;e<u.length;e++)for(var n=u[e],r=0;r<n.c.length;r++)t.key==n.c[r]&&0==n.k&&(r-2+4)%254!=n.d&&(n.d=r,n.k=!0)});let f=50;var c=500/f,d=500/c;let h=function(t,e){for(var n=[],r=0;r<e;r++){n[r]=[];for(var o=0;o<t;o++)n[r][o]=0}return n}(d,d),u=[];u.push(e(Math.floor(f/4*3),Math.floor(.8*f),.1,6,["ArrowUp","ArrowRight","ArrowDown","ArrowLeft"],{tail:"rgb(0 120 0)",head:"rgb(0 200 0)"},"green")),u.push(e(f/4,.8*f,.1,6,["w","d","s","a"],{tail:"rgb(0 0 120)",head:"rgb(0 0 200)"},"blue"));let y,g,s=[],m=0;function v(e){y=y||e,function(t,e,n){t.fillStyle="rgb(0 0 0)",t.fillRect(0,0,500,500),function(t,e,n){for(var r=0;r<e.length;r++)for(var o=0;o<e[r].length;o++)t.fillStyle="rgb(200 0 0 / 30%25)",t.fillRect(o*n,r*n,n-1,n-1)}(t,e,n),function(t,e,n){for(var r=0;r<e.length;r++)t.fillStyle="rgb(100 0 100)",t.fillRect(e[r].x*n,e[r].y*n,n,n)}(t,s,n);for(var r=0;r<u.length;r++)o(i,u[r],n)}(i,h,c),g=(e-y)/1e3;for(var l=0;l<u.length;l++){var a=u[l];g>a.v&&(y=e,r(a,s),n(a))}m+=1,m>=30&&(function(e,n){e.push({x:t(n),y:t(n)})}(s,d),m=0),requestAnimationFrame(v)}</script>
```

![Gameplay](/assets/gameplay.png)

## building
1. Clone the repository: 
```
git clone https://www.github.com/AGVtrop/squaron.git
cd squaron
```
2. Build it:
```
npm install
node build.mjs
```
3. The both the html and URI code will be in dist/

4. To change, you'll want to edit src/index.html
 - Don't forget to ```node build.mjs``` after you write the file, or nothing will happen
