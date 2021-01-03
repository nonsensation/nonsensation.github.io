---
layout: page

title: Documentation
description: >
  Getting started, FAQ & HowTo's
---

# Sideline

*A customizable scoreboard for streaming sports events.*

---

## Installation & Setup

### Requirements

Sideline uses a browser window that displays web content.  
For this to work, you currently need an external webserver running.  
You can actually use any server you want. While develping this app, I used [Z-WAMP](http://zwamp.sourceforge.net/). It also comes with an MySQL Database.

The MySQL Database is also needed at the current state of Sideline. This might all change in the future as I try to have a self containing app.

Also you need to be streaming with OBS. Other streaming clients might work too, but I haven't tested any of them and I do not know if they can capture a window.  
Also I might integrate OBS Scene switching into Sideline - it might not be possible with other clients.

### Setup Sideline

- Copy and paste the *index.html* into your webservers folder or create your own.
- In the Sideline app, go to *Settings - URL* and enter the URL where your website is served (usually `localhost:8080`).
- The contents of your index.html should now be displayed in the Sideline webview-window.

### Setup OBS

- In your Scene add a new *Source - Window Capture* and select the Sideline webview-window.  
You might choose another *Capture Method* do only display the inner content of the Sideline webview-window and not also the titlebar.
- Right click onto this new source and select *Filters*. Add a new *Chroma-Key* filter, such that  only the actuall scoreboard is visible in the preview.

## Planned Features & TODO

What I have in my mind (no particular order):

- Replace external webserver within C# .NET
- Replace MySQL database wit h a textual one (currently EntityFramework 5.0 is not compatible with FileContext)
- Self containing, no installation required exe
- More dynamic and customizable UI to adapt for different types of sports and events  
Then there is no need for 'profiles' or ideline could be used for any overlay
- Have Sideline also manage Teams/Players/Referees/Matches/Games/Tournaments for an all around solution
- Add the ability to change scenes from within Sideline over the network
- Add extenral timing sources like text files (and maybe score and other data)  
Common scoreboards in sports halls either have a wired connection to the actual display unit or via radio frequencies (433MHz). These require external solutions to intercept the current displayed data. This is an entire püroject in itself.  
Another solution to this would be an extra camera and some AI image to text neural network to get the information from the video signal and sync it with Sideline.
- Document the Javascript Callbacks
- Multiple HTML/CSS examples for scoreboards (currently 2)
- Log history of the game, export this data to existing match-protocolling software 
