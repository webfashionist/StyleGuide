# Fixes

Some statements work in some browsers but don't in others, especially for older browsers or the beloved Internet Explorer. 


## JavaScript

### `window.location.origin`

This object exists in the most browsers, but doesn't in older IE browsers. Here's a fix for that:

```javascript
if(!window.location.origin) {
    window.location.origin = window.location.protocol + '//' + window.location.hostname + (window.location.port ? ':' + window.location.port : '');
}
```


## SQL

### `GROUP BY` errors

See `GROUP BY` vs `DISTINCT` in the [SQL guideline](SQL.md#group-by-vs-distinct).