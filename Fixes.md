# Fixes

Here's a list of errors which did occur due to either the browser, browser version or server environment. 
Therefore these errors aren't really bugs, they are due to inconsistent (default) settings in the software used by either the client or the server.

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