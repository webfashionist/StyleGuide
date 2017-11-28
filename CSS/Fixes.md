# CSS fixes

## Internet Explorer

Even if it's not recommended, it is sometimes required to specify CSS settings to specific browsers only. Here's how to do it for Internet Explorer:

```css

.node {
    background: gray; /* standard */
    background: yellow\0; /* IE 11 and below */
    background: pink\9; /* IE 8 and below */
    *background: green; /* IE 7 and below */
    _background: blue; /* IE 6 */
}
```

Currently Firefox and Chrome browsers do recognize these CSS values as invalid and therefore don't use them. 

Sources: 
- [code.tutsplus.com](https://code.tutsplus.com/tutorials/quick-tip-how-to-target-ie6-ie7-and-ie8-uniquely-with-4-characters--net-10575)
- [Stackoverflow](https://stackoverflow.com/questions/8874290/how-can-i-set-css-only-for-specific-ie-browsers)