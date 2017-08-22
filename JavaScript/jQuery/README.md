# jQuery

## Table of contents

- [AJAX](#ajax)


## AJAX

AJAX calls should always be called using:

```javascript
$.ajax({
    url : "http://....",
    type: "POST|GET",
    data: {key: value},
    success: function(response) {
        // it is strongly recommended to have a JSON object as a response
        try {
            var data = JSON.parse(response);
            
        } catch(e) {
            console.error("Error: " + e.message);
        }
    },
    error: function(xhr, response, errorThrown) {
        console.error("Error: #" + xhr.status + " " + errorThrown);
    }
});
```

Additional useful methods are:

- Method called before the GET or POST request is sent:

```beforeSend: function() {}```

- `XHR` request allowing to add further event listeners, like the download progress:

```
xhr: function() {
    var xhr = new window.XMLHttpRequest();
    // download progress
    xhr.addEventListener("progress", function (evt) {
        var percentComplete;
        if (evt.lengthComputable) {
            // length computable - Content-Length defined in header
            percentComplete = evt.loaded / evt.total;
            $("#progress").stop().animate({'width': Math.round(percentComplete * 100) + "%"}, 500);
        }
    }, false);
    return xhr;
}
```

See [jQuery.ajax()](https://api.jquery.com/jQuery.ajax/) for the documentation.