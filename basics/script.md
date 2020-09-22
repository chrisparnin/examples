# Playground: JavaScript Array Operations

Simple script playground for executing JS scripts and demonstrating different JS array related operations.

### Create an array of the past seven days, inclusive:

```js |{type:'script'}
let array = [...Array(7).keys()].map(days => new Date(Date.now() - 86400000 * days));
console.log( array );
```

> There are 86400000 milliseconds in each day. The expression `[...Array(7).keys()]` will become: `[0, 1, 2, 3, 4, 5, 6]`.

### Generate a random alphanumerical 

This snippet will generate a semi-random alphanumeric ids.

```js |{type:'script'}
let id = Math.random().toString(36).substring(3);
console.log(id);
```
> Why? The random float will be converted into base 36, which will be represented with 10 digits and 26 alphanumeric characters. The `.substring(2)` will remove the leading 0.


### Return a shuffled copy of an Array-like.

```js |{type:'script'}
let fnShuffle = (arr) => arr.slice().sort(() => Math.random() - 0.5)
console.log( fnShuffle([1,2,3,4,5,6,7,8,9,10]) );
```

> If you ever needed to mix things you, this method will move things around in an array. Because `sort` will modify an array in-place, we can take advantage of the shallow copy returned by `slice`.

### Generate random color.

```js |{type:'script'}
let randomHex = '#' + Math.floor(Math.random() * 0xffffff).toString(16).padEnd(6, '0');
console.log( randomHex );
```

> Here, we generate a number between 0--16million, represented as a hexadecimal number. The final part, `padEnd`, will ensure smaller numbers are always 6 digits long.


### Remove duplicates. 

```js |{type:'script'}
let arr = [1,2,3,3];
console.log( [...new Set(arr)] );
```
> This only works with primitives but it's still nifty. Set takes any iterable object, like an array `[1,2,3,3]`, and removes duplicates. The spread operator makes that set `[1,2,3]`.


### Print keyboard.

If you ever needed a 3D ascii keyboard, here you go.

```js |{type:'script'}
let keyboard = (_=>[..."`1234567890-=~~QWERTYUIOP[]\\~ASDFGHJKL;'~~ZXCVBNM,./~"].map(x=>(o+=`/${b='_'.repeat(w=x<y?2:' 667699'[x=["BS","TAB","CAPS","ENTER"][p++]||'SHIFT',p])}\\|`,m+=y+(x+'    ').slice(0,w)+y+y,n+=y+b+y+y,l+=' __'+b)[73]&&(k.push(l,m,n,o),l='',m=n=o=y),m=n=o=y='|',p=l=k=[])&&k.join`
`)();

console.log(keyboard);
```