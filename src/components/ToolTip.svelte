

<div class="editorwindow">
    <div class="exit-btn">X</div>
<span 
data-text="goToDefinition" 
class="variablename"
>variableName<div class="childthing"><a href="#server-requests">goToDefinition</a></div></span> = newValue;</div>


<style>
    /* all mobile styles */
    .exit-btn {
	border: 2px solid black;
	height: 1.5em;
	width: 1.5em;
	margin-top: .5em;
	margin-left: .5em;
    margin-bottom: 1em;
    padding-top: .35em;
    padding-left: .2em;
    padding-right: .2em;
	font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	font-weight: 200;
	border-radius: 2px;
	background-color: white;
}
.editorwindow {
	border: 2px solid black;
	border-radius: 2px;
	width: 90%;
	margin: auto;
    margin-top: 4em;
	text-align: center;
	padding-bottom: 2em;
	font-family: 'Courier New', Courier, monospace;
	font-weight: 700;
    font-size: x-large;
	background-color: #edebf5;
    margin-bottom: 17em;
}

.editorwindow a {
    color: white;
    text-decoration: none;
}

.variablename {
  position:relative; /* making the .tooltip span a container for the tooltip text */
  border-bottom:1px dashed #000; /* little indicater to indicate it's hoverable */

}

.childthing{
display: none;
}

.editorwindow:hover .childthing{
 
  position:absolute;

  /* vertically center */
  top:50%;
  transform:translateY(-50%);
  
  /* move to right */
  left:100%;
  margin-left: -5em;
  margin-top: -2em;
  
  /* basic styles */
  width:200px;
  padding:10px;
  border-radius:10px;
  background:#000;
  color: #fff;
  text-align:center;

  display:block; 
}
 
/* .tooltip:hover::after {
  display:block;
} */

/* source: https://blog.logrocket.com/creating-beautiful-tooltips-with-only-css/ */

/* Add animation (fade in the popup) */
@-webkit-keyframes fadeIn {
  from {opacity: 0;}
  to {opacity: 1;}
}

@keyframes fadeIn {
  from {opacity: 0;}
  to {opacity:1 ;}
}

    /* all desktop styles */
    @media (min-width: 1100px) {
    .exit-btn {
	border: 2px solid black;
	height: 1.5em;
	width: 1.5em;
	margin-top: .5em;
	margin-left: .5em;
    margin-bottom: 1em;
    padding-top: .35em;
    padding-left: .2em;
    padding-right: .2em;
	font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	font-weight: 200;
	border-radius: 2px;
	background-color: white;
}
.editorwindow {
	border: 2px solid black;
	border-radius: 2px;
	width: 40%;
	margin: auto;
    margin-top: 4em;
	text-align: center;
	padding-bottom: 4em;
	font-family: 'Courier New', Courier, monospace;
	font-weight: 700;
    font-size: x-large;
	background-color: #edebf5;
    margin-bottom: 17em;
}

.editorwindow a {
    color: white;
    text-decoration: none;
}

.variablename {
  position:relative; /* making the .tooltip span a container for the tooltip text */
  border-bottom:1px dashed #000; /* little indicater to indicate it's hoverable */

}

.childthing{
display: none;
}

.editorwindow:hover .childthing{
 
  position:absolute;

  /* vertically center */
  top:50%;
  transform:translateY(-50%);
  
  /* move to right */
  left:100%;
margin-left: -2em;
  margin-top: -2em;
  
  /* basic styles */
  width:200px;
  padding:10px;
  border-radius:10px;
  background:#000;
  color: #fff;
  text-align:center;

  display:block; 
}
 
/* .tooltip:hover::after {
  display:block;
} */

/* source: https://blog.logrocket.com/creating-beautiful-tooltips-with-only-css/ */

/* Add animation (fade in the popup) */
@-webkit-keyframes fadeIn {
  from {opacity: 0;}
  to {opacity: 1;}
}

@keyframes fadeIn {
  from {opacity: 0;}
  to {opacity:1 ;}
}

    }

</style>