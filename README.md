impress.js-progress
===================

Progressbar and pagexounter for impress.js presentations
Requires the steps to be submitted on impress:init event, see https://github.com/bartaz/impress.js/pull/235 and https://github.com/bartaz/impress.js/issues/232 for details.

Usage
-------------------
Add a div for progressbar and/or progress as you can see it here:

	<div class="progressbar"><div></div></div>
	<div class="progress"></div>

include the CSS in the header 

    <link href="css/impress-progress.css" rel="stylesheet" />

and include the script

	<script src="js/impress-progress.js"></script>
	
just before including impress.js.

That's it.

Feel free to change the style of your progressbar as you like by editing the CSS file.

Note
---------------------
Until m42e/impress.js@f367c84 isn't accepted there's the need to patch js/impress.js to add the steps data to init().

Changing line 402 like this:

	triggerEvent(root, "impress:init", { api: roots[ "impress-root-" + rootId ] });
	triggerEvent(root, "impress:init", { api: roots[ "impress-root-" + rootId ], steps: steps });
