![globjects Logo](globjects-logo.png "globjects")

*globjects* is an [MIT licensed](http://opensource.org/licenses/MIT), cross-platform C++ wrapper for [OpenGL API](http://www.opengl.org) objects.

*globjects* provides object-oriented interfaces to the OpenGL API (3.0 and higher).
It reduces the amount of OpenGL code required for rendering and facilitates coherent OpenGL use by means of an additional abstraction layer to [glbinding](https://github.com/cginternals/glbinding) and [GLM](https://github.com/g-truc/glm). Common rendering tasks and processes are automated and missing features of specific OpenGL drivers are partially simulated or even emulated at run-time.


## Integration of a new Documentation

The following manual steps are necessary for each added documentation:

1. Create a subfolder with the name of the release identifier (e.g., master, v2.0)
2. Copy contents of Doxygen html folder into directory
3. Add documentation meta data to ```docs/docs.pug```
4. Adjust the sort order of the documentations array in the config file; the order is used for display
5. Adjust doxy-boot.js
   1. Add code to generate backlink in the ```$(document).ready``` callback
   
The resulting head of the file should look like this:

```js
$( document ).ready(function() {
    $("#projectlogo").each(function() {
        var td = $(this);
        td.html($("<a>").attr("href", "/").append(td.html()));
    });
    
    // ...
});
```
