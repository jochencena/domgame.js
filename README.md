# domgame.js
A JS library for creating games using the HTML DOM.

# Download
<a href="https://raw.githubusercontent.com/yikuansun/domgame.js/master/domgame.js" download>https://raw.githubusercontent.com/yikuansun/domgame.js/master/domgame.js</a>

# Documentation

<h2>unit_type</h2>
<code>DOMgame.unit_type</code> is a string specifying the unit of display used in the game. This can be any CSS unit, such as px, vw, or vmin. The default unit is px. It is recommended that this variable only be changed once and at the very top of the program, because different units do not mesh well.

<h2>Gamepieces</h2>
The following functions are used to create gamepieces, or objects in the game:
<pre>
DOMgame.newEllipsePiece(gamescreen_element, x_radius, y_radius, center_x, center_y, fill_color)
DOMgame.newRectPiece(gamescreen_element, width, height, center_x, center_y, fill_color)
DOMgame.newImgPiece(gamescreen_element, width, height, center_x, center_y, imageurl)
DOMgame.newSpritePiece(gamescreen_element, width, height, center_x, center_y, spritesheeturl, spritesheetwidth, spritesheetheight, spritetop, spriteleft)
</pre>
These functions all return an HTML element, which can be edited as such.
Ex.: <code>player = DOMgame.newRectPiece(document.body, 10, 10, 50, 50, "red"); player.style.border = "solid 1vmin blue";</code>
<code>gamescreen_element</code> refers to the parent DIV of the gamepiece. It should be an HTML element. This can be another gamepiece. <code>center_x</code> and <code>center_y</code> are floats telling the position of the gamepiece. x = 0 is the very left of the gamescreen element, where as y = 0 is the very bottom. x goes from left to right; y goes from bottom up.

<h2>Functions</h2>
The following functions can be used on gamepieces:
<pre>
setXpos(xpos)
setYpos(ypos)
changeXpos(change_by)
changeYpos(change_by)
rectCollision(otherobject)
directionalCollision(otherobject)
</pre>
Ex.: <code>if (player.rectCollision(bigsquare)) { player.setXpos(1) }</code>
These functions can technically be used on any HTML element, but they are recommended to only be used with gamepieces created using domgame.js.
<code>rectCollision</code> returns true or false, whereas <code>directionalCollision</code> returns a direction: top, right, bottom, left, and false, if there is no collision. 
There is also an alternative set of collision scripts: <a href="https://github.com/yikuansun/Alternative-collision-script-for-domgame.js">https://github.com/yikuansun/Alternative-collision-script-for-domgame.js</a>.
<code>changeXpos</code> and <code>changeYpos</code> change the X position or Y position of the gamepiece positively by the input of the function.
<br/>
<br/>
<br/><a href="https://github.com/yikuansun/Scrolling-platformer-demo-with-domgame.js/archive/master.zip">Download a sample side-scrolling platformer created with domgame.js</a>
