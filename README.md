<!DOCTYPE html> 
<html>
  <head>
<script type="text/javascript">
// <![CDATA[
var speed=33; // lower number for faster
var flakes=100; // number of flakes
var colour="#FFF"; // colour of flakes
var slush=20; // set to '0' for no slush or otherwise set to height at which slush melts
var over_or_under="over"; // set to "over" for snow to always be on top, or "under" to allow it to float behind other objects

/***************************\
*     Let It Snow Effect    *
*(c)2004-13 mf2fm web-design*
*  http://www.mf2fm.com/rv  *
* DON'T EDIT BELOW THIS BOX *
\***************************/
var flks=new Array();
var flkx=new Array();
var flky=new Array();
var fldy=new Array();
var slss=new Array();
var slsh=new Array();
var swide, shigh, boddie;

function addLoadEvent(funky) {
  var oldonload=window.onload;
  if (typeof(oldonload)!='function') window.onload=funky;
  else window.onload=function() {
    if (oldonload) oldonload();
    funky();
  }
}

addLoadEvent(baby_its_cold_outside);

function baby_its_cold_outside() { if (document.getElementById) {
  var i;
  boddie=document.createElement("div");
  i=boddie.style;
  i.position="fixed";
  i.top="0px";
  i.left="0px";
  i.overflow="visible";
  i.width="1px";
  i.height="1px";
  i.backgroundColor="transparent";
  document.body.appendChild(boddie);
  set_width();
  for (var i=0; i<flakes; i++) {
    flks[i]=createDiv(3, 3, colour);
    flkx[i]=3*Math.floor(Math.random()*swide/3);
    flky[i]=Math.floor(Math.random()*shigh);
    fldy[i]=2+Math.floor(Math.random()*4);
    flks[i].style.left=flkx[i]+"px";
    flks[i].style.top=flky[i]+"px";
	flks[i].style.zIndex=(over_or_under=="over")?"1001":"0";
    boddie.appendChild(flks[i]);
  }
  setInterval("let_it_snow()", speed);
}}

function createDiv(height, width, colour) {
  var div=document.createElement("div");
  div.style.position="absolute";
  div.style.height=height+"px";
  div.style.width=width+"px";
  div.style.overflow="hidden";
  div.style.backgroundColor=colour;
  return (div);
}

window.onresize=set_width;
function set_width() {
  var sw_min=999999;
  var sh_min=999999;
  if (document.documentElement && document.documentElement.clientWidth) {
    if (document.documentElement.clientWidth>0) sw_min=document.documentElement.clientWidth;
    if (document.documentElement.clientHeight>0) sh_min=document.documentElement.clientHeight;
  }
  if (typeof(self.innerWidth)=='number' && self.innerWidth) {
    if (self.innerWidth>0 && self.innerWidth<sw_min) sw_min=self.innerWidth;
    if (self.innerHeight>0 && self.innerHeight<sh_min) sh_min=self.innerHeight;
  }
  if (document.body.clientWidth) {
    if (document.body.clientWidth>0 && document.body.clientWidth<sw_min) sw_min=document.body.clientWidth;
    if (document.body.clientHeight>0 && document.body.clientHeight<sh_min) sh_min=document.body.clientHeight;
  }
  if (sw_min==999999 || sh_min==999999) {
    sw_min=800;
    sh_min=600;
  }
  swide=sw_min-3;
  shigh=sh_min;
  if (slush) {
    if (swide/3>slss.length) for (i=slss.length; i<swide/3; i++) {
      if (!slsh[i]) slsh[i]=3;
      slss[i]=createDiv(slsh[i], 3, colour);
      boddie.appendChild(slss[i]);
    }
    for (i=0; i<swide/3; i++) {
      slss[i].style.height=slsh[i]+"px";
      slss[i].style.top=shigh-slsh[i]+"px";
      slss[i].style.left=3*i+"px";
    }
    if (i<slss.length && slss[i].style.left!="-3px") for (; i<slss.length; i++) slss[i].style.left="-3px";
  }
}

function let_it_snow(c) {
  var i, x, o=0, z=0;
  for (i=0; i<flakes; i++) {
    flky[i]+=fldy[i];
	x=Math.floor(flkx[i]/3);
    if (slush) {
      o+=slsh[x];
      if (flky[i]>=shigh-slsh[x]) {
        if (x<swide && slsh[x]>slsh[x+1]+3) x++;
        else if (x>0 && slsh[x]>slsh[x-1]+3) x--;
        slss[x].style.top=shigh-(slsh[x]+=3)+"px";
        slss[x].style.height=slsh[x]+"px";
		flky[i]=shigh;
	  }
    }
    if (flky[i]>=shigh || flkx[i]>swide) {
	  flky[i]=0;
	  fldy[i]=2+Math.floor(Math.random()*4);
	  flkx[i]=3*Math.floor(Math.random()*swide/3);
	  flks[i].style.left=flkx[i]+"px";
	  z++;
	}
	flks[i].style.top=flky[i]+"px";
  }
  if (o>flakes*slush) for (i=0; i<slsh.length; i++) if (slsh[i]>3) slsh[i]--;
  if (z || o>flakes*slush) set_width();
}
// ]]>
</script>
  <body style="background-color: #faebf8;">
    <title>SEBBY!</title> 
<div id="end">
    <img src="https://64.media.tumblr.com/4dd39de9139b9f606235478a2815e580/aa6b7226403ed707-63/s250x400/f9669d8f7b78679dd7b8cd3b7d853aca04918b4a.gifv" alt="button" width="125" height="20">
    </div>
    
   <div id="wobble"><p>Hello,, for Sebby<br/>
     Have some cool Pokemon</p></div>

      <Poke>
    <img src="https://64.media.tumblr.com/abc912db37cd88e5915c4298366422ee/085f80c41f3ef352-3f/s75x75_c1/fc30a7d8da037d6715a7fbd3a05b6055e008a096.gifv">
    <img src=https://64.media.tumblr.com/302589f423bb984594de2731386cd9f7/085f80c41f3ef352-a1/s75x75_c1/4acfd4bfd845cc2e926dbb44b21374ef9c440f79.gifv>
      <img src="https://64.media.tumblr.com/e4440bdeefac8ebaaf95a417444b6129/085f80c41f3ef352-36/s75x75_c1/38960d3e056e63359365b7342a1ddf3b0d1f2036.gifv">
      <img src=https://64.media.tumblr.com/78dff8a64089e7c04226b131d04595eb/085f80c41f3ef352-b8/s75x75_c1/20d4b75abb906952d7131c36726a60887311f1f8.gifv>
      <img src=https://64.media.tumblr.com/fa39c473c35e414515d3b177548d0463/085f80c41f3ef352-6b/s75x75_c1/f68ede9f5a82e0768dcbe081c6935a4c0f0627c4.gifv></Poke> 
    </div>
      
    
  <p>Some fun links for you!!!</p> 
      <div class="link">
      <a href="https://pointerpointer.com/">Surprise!</a>
      <a href="https://weirdscifi.ratiosemper.com/hampsterdance/hampsterdance.html">Hamster??</a> 
      <a href="https://www.my90stv.com/#5QlXCKLFRmk">OLD</a>
      <a href="http://www.windows93.net/">Supa Surprise</a>
        <a href="http://www.jellotime.com/">Jello Jello</a>
    </div>
      <p>Have a good day ♡</p>
      <div id="end">
<img src="https://64.media.tumblr.com/0f15a9fee59ff955aa873afc34f3db2a/tumblr_inline_mlw1h3sSo41qz4rgp.gif">
    </div>
</head>
