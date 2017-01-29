# Start Youtube playlist with random video

I guess that _everyone_ came across this problem at one point
> I want to embed a Youtube playlist starting from random video
- Everyone

Youtube does not have an option for that and I didnt find a solution on the internet, so here it is.

```javascript
// Playlist ID
    var list = 'PLz8JsiLUtVnD2t0qlJYDhXtyiCWTv37DA'
// Random number generator 
    var num = Math.floor(Math.random() * 200 + 1);
// Embed video code
    document.writeln('<iframe id="random-video" src="//www.youtube.com/embed/videoseries?list=' + list + '&index=' + num + '&autoplay=1&controls=0&modestbranding=1&showinfo=0" frameborder="0" allowfullscreen></iframe>');
```
[DEMO] (https://borkosavic.github.io/random-youtube-playlist-video)

## Options:
### Playlist ID
ID of playlist you want to embed, you can find it out by sharing a playlist. Always start with PL. 
### Random number generator 
Generate a random number which will be used to select video to start playlist with. Playlist used in this example currently has 200 videos, you need to change this value to number of videos in the paricular playlist you are embeding
### Embed video code 
Generates embed code. Note that I added some parameters:
1. Autoplay - on
2. Controls - off (hides Youtube controls)
3. Modest branding (reduces Youtube branding to transparent logo in bottom right corner)
4. Show info - off (hides song/playlist info usually displayed in top left corner)
You can find full list of available parameters at [YouTube Embedded Players and Player Parameters] (https://developers.google.com/youtube/player_parameters)
### Fullscreen stuff - optional
```javascript
$(function(){
    $('#random-video').css({ width: $(window).innerWidth() + 'px', height: $(window).innerHeight() + 'px' });
    $(window).resize(function(){
      $('#random-video').css({ width: $(window).innerWidth() + 'px', height: $(window).innerHeight() + 'px' });
    });
});
```
This is jquery code that can be found all around the interwebs - it makes embeded video take full width & height of the browser vindow. Note that you need to include jQuery before this part in order for it to work properly. 


Happy embeding! :)

