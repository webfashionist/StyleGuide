# JavaScript fixes

## `window.location.origin`

This object exists in the most browsers, but doesn't in older IE browsers. Here's a fix for that:

```javascript
if(!window.location.origin) {
    window.location.origin = window.location.protocol + '//' + window.location.hostname + (window.location.port ? ':' + window.location.port : '');
}
```