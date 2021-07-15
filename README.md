<h1 align="center"> Claudio Castorina's Portfolio </h1>
<img src="https://i.imgur.com/z0np2ao.jpg">
<h2> Introduction </h2>
<p><a href="https://www.claudiocastorina.com">This</a> is my personal creative portfolio to show some of my web development projects. It was developed in <a href="https://vuejs.org/">Vue.js 3</a>, a framework based on <a href="https://www.javascript.com/">Javascript.</a> It consists of App.vue and 4 components: Navbar, Header, Terminal and Projects.</p>
<h2> Components </h2>
<h4> Navbar </h4>
<p> The navbar component is really simple, it's composed of two anchors "About" and "Projects", which upon clicking emit an event that will then open the required section. </p>
<h4> Header </h4>
<p> This component is also very simple. It contains a short description about me and the possibility of opening the "About" section via an anchor in the description itself. </p>
<h4> Terminal </h4>
<p> This component is more advanced than the previous ones. It is used to simulate the call of a property of a hypothetical object "Claudio" (me!), within a terminal created in CSS. Once this is done, all the data entered in App.vue is looped, and the possibility of going to the projects or closing the terminal is inserted.</p>
<h4> Projects </h4>
<p>This is the central part of the site, the data entered in App.vue is looped to create the various project divs, with all the information entered. All this is of course made presentable in CSS.</p>
