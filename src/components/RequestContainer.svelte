<div class="animation-request-container">
    <div class="request-container">
      
          <div class="request">Request 1</div>
      <div class="request-path">
          <div class="requestBox"></div>
          <div class="client">Client</div>
      </div>
      </div>
      <div class="server">Server</div>
      <div class="request-container">
          <div class="request">Request 2</div>
      <div class="request-path">
          <div class="requestBox"></div>
      </div>
      </div>

      <div class="request-controls">
          <button class="play"> Send</button>
          <button class="pause"> Pause</button>
      </div>
  </div>

  <style>

@media (prefers-reduced-motion) {
    .animation-request-container {
	display: none;
}
}
    /* all mobile styles */
     .request-controls{
		margin: auto;
		margin-top: 3em;
	}

.animation-request-container {
	margin: auto;
    margin-top: 2em;
    margin-left: .75em;
    width: 50%;
	padding: 2em;
}

.client {
	margin-left: -5em;
    margin-top: 1.5em;
    padding: .5em;
	background-color: #edebf5;
	color: black;
	border: 3px solid  black;
	width: 3em;
	height: 1em;
	border-radius: 20px;
	text-align: center;
    font-size: x-large;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.request {

    font-size: small;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
.request-container {
	margin: auto;
	width: 50%;
	padding: 1em;
}

.request-controls{
    display: flex;
    justify-content: space-between;
	margin: auto;
	width: 50%;

}
.request-path	{
	height: 1em;
	width: 8em;
	background-color: white;
	margin: 1em;
	align-content: center;
	border:dashed 4px gainsboro;
	border-top-left-radius: 255px 120px;
    border-top-right-radius: 120px 225px;
    border-bottom-right-radius: 225px 120px;
    border-bottom-left-radius:120px 255px;
}

.requestBox {
  width: 0;
  height: 0;
  margin-top: -.5em;
  margin-left: -.5em;
  border-top: .75em solid transparent;
  border-bottom: .75em solid transparent;
  border-left: 1.25em solid #4b0d82;

}
.play {
	height: 2em;
    color: white; /* Background color */
    background-color: #4b0d82; /* Text color */
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
	font-size: x-large;
    border: 1px solid #4b0d82;
}

.play:hover {
    color: #4b0d82; /* Change background color on hover */
    background-color: white; /* Text color */
    border: 1px solid #4b0d82;
}

.pause {
    border: 1px solid #4b0d82;
	height: 2em;
    color: white; /* Background color */
    background-color: #4b0d82; /* Text color */
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
	font-size: x-large;
}

.pause:hover {
    color: #4b0d82; /* Change background color on hover */
    background-color: white; /* Text color */
    border: 1px solid #4b0d82;
}


.server {
	margin-left: 7em;
    padding: .5em;
	background-color: #fce8d7;
	color: black;
	border: 3px solid  black;
	width: 3em;
	height: 1em;
	border-radius: 20px;
	text-align: center;
    font-size: x-large;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
/* all desktop styles */
@media (min-width: 1100px) {
    .request-controls{
		margin: auto;
		margin-top: 3em;
	}

.animation-request-container {
	margin: auto;
    width: 50%;
	padding: 2em;
}

.client {
	margin-left: -8em;
	margin-top: 1em;
	padding-top: .5em;
	background-color: #edebf5;
	color: black;
	border: 3px solid  black;
	width: 6em;
	height: 3em;
	border-radius: 20px;
	text-align: center;
    font-size: x-large;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.request {
	margin-bottom: 1em;
    font-size: x-large;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
.request-container {
	margin: auto;
	width: 50%;
	padding: 0;
}

.request-controls{
    padding-top: 2em;
	padding-left: -4em;
    padding-bottom: 6em;
	margin: auto;
    margin-left: 9.25em;
	width: 50%;

}
.request-path	{
	height: 1em;
	width: 270px;
	background-color: white;
	margin: .5em;
	align-content: center;
	border:dashed 4px gainsboro;
	border-top-left-radius: 255px 120px;
    border-top-right-radius: 120px 225px;
    border-bottom-right-radius: 225px 120px;
    border-bottom-left-radius:120px 255px;
}

.requestBox {
  width: 0;
  height: 0;
  margin-top: -.5em;
  margin-left: -.5em;
  border-top: .75em solid transparent;
  border-bottom: .75em solid transparent;
  border-left: 1.25em solid #4b0d82;

}
.play {
	margin-top: 2em;
    margin: auto;
	height: 2em;
    color: white; /* Background color */
    background-color: #4b0d82; /* Text color */
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
	font-size: x-large;
    border: 1px solid #4b0d82;
}

.play:hover {
    color: #4b0d82; /* Change background color on hover */
    background-color: white; /* Text color */
    border: 1px solid #4b0d82;
}

.pause {
    border: 1px solid #4b0d82;
	margin: auto;
	height: 2em;
    color: white; /* Background color */
    background-color: #4b0d82; /* Text color */
    cursor: pointer;
    transition: background-color 0.3s ease;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
	font-size: x-large;
}

.pause:hover {
    color: #4b0d82; /* Change background color on hover */
    background-color: white; /* Text color */
    border: 1px solid #4b0d82;
}


.server {
	margin-top: 1em;
	margin-left: 21em;
	padding-top: .5em;
	background-color: #fce8d7;
	border: 3px solid  black;
	width: 6em;
	height: 3em;
	border-radius: 20px;
	text-align: center;
	color: black;
    font-size: x-large;
	font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
}
  </style>