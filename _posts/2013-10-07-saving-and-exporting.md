---
{date: 2013-10-07, language: en, title: Saving and Exporting, tumblr_id: 63367326864}
---

<p>Many programs with save functionality go out of their way to make a distinction between "Save" and "Export".&nbsp;The main reasoning for separating them is that "export" saves to file formats that do not support the full range of the application's internal data structure, meaning that if I save to a file format available under the "export" option, reopening the file will not give me all the same data as I had previously.</p>
<p>An example of this is in image manipulation programs such as The GIMP and Photoshop, where "save" gives you XCF's or PSD's, which contain full RGBA/CMYKA/Raw/etc color coded images with full layer information, masks, filters, paths, etc, etc., whereas exporting to JPEG means flattening the layers, reducing to RGB, and losing a lot of the layout detail.</p>
<p>The issue is that most people who are using these programs fall into broadly two categories:</p>
<p>A) Those who don't know much about image manipulation and just want to do rudimentary editing on photos and such, like cropping, resizing, color correction, and so on, and get a fixed JPEG or PNG output.</p>
<p>B) Those who do know a lot about image manipulation, want the full range of features, and know the difference between different file formats.</p>
<p>There is an intermediary group there who are transitioning from A to B. The question is, how to best cater to the needs of these three groups?</p>
<p>Group "A" would be happiest with everything under the "save" function, with the saving file format of files being opened for editing set to whatever the file was that was opened. These users will want some guidance on appropriate file formats for new images - for instance, not having a default option, but having XCF/PSD at the top of the list, and JPEG, PNG and such labeled below as being "Web safe" or something like that.</p>
<p>Group "B" is presumably nuanced enough to be able to use a single "save" dialog correctly, even in the face of added complexity from there being a couple of different outcome motifs<span>.</span></p>
<p><span>The intermediate group will learn fastest if there is some kind of information provided on the difference. This information is not in any way conveyed by there being two save buttons, one called "Save" and the other called "Export". Specifically: people who do not understand internal data structures of applications are not likely to understand why this distinction is being made, will not care, and are likely to be frustrated by this (to them) vacuous distinction.</span></p>
<p>However... simply alerting people to the fact that there will be data loss on certain file formats in the save box in a subtle way is way more likely to work for unexperienced users. For instance, a little status line at the bottom of the save box could change depending on which format you select, and say:</p>
<p>XCF selected -&gt; "Supports every feature. Not usable on the web."</p>
<p>JPG selected -&gt; "Supports RGB. Does not support layers, paths, filters, alpha. Usable on the web."</p>
<p>PNG selected -&gt; "Supports RGBA, layers... Usable on the web."</p>
<p>You get the idea. Be informative and explicit, but not cluttery, and don't assume that datastructure level distinctions are meaningful to the user.</p>
