# How to check if an image exists on the server
A simple way of check if an image exists on the server and
do something with it using javascript is using the `onerror()`
callback naturally present on image element.

Here an example where you can hide an image entirely if the image
doesn't load properly
```
function checkImage(src, good, bad) {
	let img = new Image();
		img.onload = good;
		img.onerror = bad;
		img.src = src;
}

checkImage(path, function() { alert("good") }, function() { alert("bad") });
```
Another way is to put everything already inside of an html tag.
The next example let you hide the image if the src doesn't exists
```
<img onerror="this.style.display = 'none';" src=path />
```

This last example let you replace the image with a fallback
if the image doesn't exist
```
<img onerror="this.src = <fallback>" src=path />
```