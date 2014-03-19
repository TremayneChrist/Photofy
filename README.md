## Getting Started

First thing to do, is to [download the latest version of Photofy](https://github.com/TremayneChrist/Photofy/downloads). Once you have the latest code, you need to add a containing div element and give it an id or class name so that it can be referenced. This container needs to have some css styling work done on it, otherwise when you initialize Photofy, you will just have a long line of images changing around.

```css
<style type="text/css">
#photofy
{
    width: 506px;
    height: 304px;
}

#photofy a.photofy_thumbnail
{
    border: 1px solid #eee;
    display: block;
    float: left;
    text-decoration: none;
    width: 100px;
    height: 100px;
    margin: 0 -1px -1px 0;
}

#photofy a img
{
    border: none;
    width: 100px;
    height: auto;
}
</style>
<div id="photofy"></div>
```

Next, you need to create an image list. This list contains the thumbnail image url, thumbnail link url and HTML content used for the gallery info panel. This list is a Photofy object array which should follow the following design pattern.

```javascript
[{"ImageUrl":"/Path/Thumbnails/1.jpg","LinkUrl":"/Path/1.jpg","HTML":"<h1>Image 1</h1>"}]
```

To do this you can use the [Image List Generator](http://tremaynechrist.co.uk/Photofy/Generator), however, for more advance solutions, this should be generated in a controller or code-behind and returned as a JSON Result.

```html
<script type="text/javascript"> // Using an image list
    var images = [{"ImageUrl":"/Path/Thumbnails/1.jpg","LinkUrl":"/Path/1.jpg","HTML":"<h1>Image 1</h1>"}];
    $("#photofy").photofy({
        imageSource: images;
    });
</script>

<script type="text/javascript"> // Using a JSON result
    $("#photofy").photofy({
        imageSource: "/myImageSource.json"
    });
</script>
```

Included in the [download](https://github.com/TremayneChrist/Photofy/downloads) is a demo page showing it all in action. For more configurable options, view the [configurable options](https://github.com/TremayneChrist/Photofy/wiki/Configurable-Options) page.
