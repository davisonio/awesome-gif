# Awesome GIF


## Command-line Tools 
- [ffmpeg](https://www.ffmpeg.org)
- [ImageMagick](http://www.imagemagick.org/)
- [GraphicsMagick](http://www.graphicsmagick.org/) - *GraphicsMagick is usually faster than ImageMagick*
- [MoviePy](http://zulko.github.io/moviepy/)
- [Gifsicle](https://github.com/pornel/giflossy)
- [Gif.js](https://github.com/jnordberg/gif.js)

## GUI
- [Glyph](http://www.glyph.video/) - *using MoviePy*

## Hosting
- [Gfycat](http://gfycat.com) - *Maximum gif/video length: 15 seconds.  Maximum file upload is 300Mb*
- [Imgur](http://imgur.com) - *Maximum file upload is 50MB*

## Online tool
- [Vid2gif](http://imgur.com/vidgif) by imgur
- [EzGif](http://ezgif.com/)



## Scripts


### Frames to gif 

```bash
ffmpeg -f image2 -i image%d.jpg animated.gif
```

```bash
convert   -delay 20   -loop 0   frames*.png   animated.gif
```

### Gif to frames

```bash
ffmpeg -i video.mpg image%d.jpg
```
```bash
convert -coalesce animated.gif image%05d.png
```

### High quality gif with ffmpeg / based on this [article](http://blog.pkh.me/p/21-high-quality-gif-with-ffmpeg.html)

- Generate a palette :

```bash
#!/bin/sh
start_time=30
duration=3
ffmpeg -y -ss $start_time -t $duration -i input.avi \
-vf fps=10,scale=320:-1:flags=lanczos,palettegen palette.png
```
- Output the GIF using the palette :

```bash
#!/bin/sh
start_time=30
duration=3
ffmpeg -ss $start_time -t $duration -i input.avi -i palette.png -filter_complex \
"fps=10,scale=320:-1:flags=lanczos[x];[x][1:v]paletteuse" output.gif
```
[article](http://blog.pkh.me/p/21-high-quality-gif-with-ffmpeg.html)

### Optimize Gif 

```
convert -layers Optimize output.gif output_optimized.gif
```

### Lossy GIF Compressor 

```bash
./gifsicle -O3 --lossy=80 -o lossy-compressed.gif input.gif

```
[Lossy Gif](http://pornel.net/lossygif)


### Making gif from video  

```python
from moviepy.editor import *

clip = (VideoFileClip("input.avi")
        .subclip((4,00.00),(5,00.00))
        .resize(0.3))
clip.write_gif("output.gif")

```
[article](http://zulko.github.io/blog/2014/01/23/making-animated-gifs-from-video-files-with-python/#converting-a-video-excerpt-into-a-gif)

### Freezing a region / Cinemagraphs 

```python
from moviepy.editor import *
                   
clip = (VideoFileClip("input.avi")
        .subclip((4,00.00),(5,00.00))
        .resize(0.3)
        .fx(vfx.freeze_region, outside_region=(170, 230, 380, 320)))
clip.write_gif("output.gif", fps=15)
```
[article](http://zulko.github.io/blog/2014/01/23/making-animated-gifs-from-video-files-with-python/#freezing-a-region)

### Perfect Loop

```python
import moviepy.editor as mp
from moviepy.video.tools.cuts import FramesMatches

clip = mp.VideoFileClip("input.avi").resize(0.3)
scenes = FramesMatches.from_clip(clip, 10, 3)

selected_scenes = scenes.select_scenes(2, 1, 4, 0.5)
selected_scenes.write_gifs(clip.resize(width=450), "./outputs_directory")
    
```
[article](http://zulko.github.io/blog/2015/02/01/extracting-perfectly-looping-gifs-from-videos-with-python-and-moviepy/)

### Javascript GIF encoder in browser

```javascript
var gif = new GIF({
  workers: 2,
  quality: 10
});

gif.addFrame(imageElement);
/**
.... add more image
**/

gif.on('finished', function(blob) {
  window.open(URL.createObjectURL(blob));
});

gif.render();
```
[Gif.js](https://github.com/jnordberg/gif.js)


### Youtube video to Gif

- with youtube-dl and then moviepy :

```
youtube-dl https://www.youtube.com/watch?v=V2XpsaLqXc8
```

[Youtube-dl](https://rg3.github.io/youtube-dl/)

- with [vid2gif](http://imgur.com/vidgif) online - [source](https://github.com/jimgur/gif)






### speed

[see this stackoverflow's answer](http://superuser.com/a/569967)

### Grabbing each frame of an HTML5 Canvas

using [PhantomJS](http://phantomjs.org/)

```javascript
var webPage = require('webpage');
var fs = require('fs');
var page = webPage.create();

var MAX_FRAMES = 100;
var current = 0;

page.open('http://www.effectgames.com/demos/canvascycle/?sound=0', function(status) {
  if (status === "success") {

      for(i=0; i < MAX_FRAMES; i++){
        setTimeout(function(){
          var frame = page.evaluate(function() {
           return document.getElementById('mycanvas').toDataURL("image/png").split(",")[1];
          });
          fs.write("./frame-" + current + ".png",atob(frame), 'wb');
          current++;
        },1000+200*i);
      }
      setTimeout(function() {
        phantom.exit();
      }, 1000*200*MAX_FRAMES);

  }
});
```

### Create a gif using built in HTML5 webcam 

with [gifie](https://github.com/eirikb/gifie). [Demo](http://eirikb.github.io/gifie/).


### Others thing

[Webkit request : add a function to WebKit to stop all in-progress GIF animations](https://bugs.webkit.org/show_bug.cgi?id=23945)





