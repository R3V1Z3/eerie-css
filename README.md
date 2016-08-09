# Eerie CSS

Dead simple, this is just an HTML page with some CSS to achieve a sort of shaky, old film effect. It's somewhat like the flickering effect seen in games like Limbo (http://store.steampowered.com/app/48000/), done solely with CSS and CSS transitions.

Some other elements have been added for effect, such as fonts and hover effects.

Example of CSS in use here:
http://hid.ugotsta.com/

## What's involved

The page is composed of simple HTML and some CSS3 stlying and animations. No JavaScript is involved.

# Flickering background

The background flicker is achieved using a CSS animation on a div with absolute positioning and with a soft, radial gradient for the background. The div is given an id of 'shakewrap'.

Flicker Animation:
```css
@-webkit-keyframes bigshakes {
    0% {
        -webkit-transform: translate(2px, -8px) rotate(-1deg);
    }
    50% {
        -webkit-transform: translate(-9px, 10px) rotate(-18deg);
    }
    100% {
        -webkit-transform: translate(6px, -2px) rotate(1deg);
    }
}
```

Shakewrap styling:
```css
#shakewrap {
    z-index: 1;
    background-color: #f00;
    height: 100vmax;
    width: 120%;
    position: fixed;
    top: -20px;
    left: -20px;
    pointer-events: none;
    animation: 'bigshakes' 0.1s linear;
    -moz-animation: 'bigshakes' 0.1s linear;
    -webkit-animation-name: 'bigshakes';
    -webkit-animation-duration: 0.1s;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-timing-function: linear;
    opacity: 0.5;
    background: -moz-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 65%, rgba(0, 0, 0, 1) 100%);
    background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, rgba(0, 0, 0, 0)), color-stop(65%, rgba(0, 0, 0, 1)), color-stop(100%, rgba(0, 0, 0, 1)));
    background: -webkit-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 65%, rgba(0, 0, 0, 1) 100%);
    background: -o-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 65%, rgba(0, 0, 0, 1) 100%);
    background: -ms-linear-gradient(top, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 65%, rgba(0, 0, 0, 1) 100%);
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 65%, rgba(0, 0, 0, 1) 100%);
}
```

# Shaky hover effect

Anchor links are given a subtle shake effect when hovered over, again using a CSS animation.

Shake animation:
```css
@-webkit-keyframes shakes {
    0% {
        -webkit-transform: translate(2px, 1px) rotate(1deg);
    }
    50% {
        -webkit-transform: translate(-1px, 1px) rotate(0deg);
    }
    100% {
        -webkit-transform: translate(1px, -2px) rotate(0deg);
    }
}
```

Hover styling:
```css
a:hover {
    text-shadow: 0px 0px 18px rgba(255, 0, 0, 1);
    animation: 'shakes' 0.1s linear;
    -moz-animation: 'shakes' 0.1s linear;
    -webkit-animation-name: 'shakes';
    -webkit-animation-duration: 0.1s;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-timing-function: linear;
}
```

# Glow effect

A subtle glow effect is used for the container div wrapping the text. It relies on a simple transition which is then applied in the container's styling.

Glow animation:
```css
@-webkit-keyframes glow {
    0% {
        box-shadow: 0px 0px 40px rgba(255, 255, 255, 0.5);
    }
    50% {
        box-shadow: 0px 0px 20px rgba(255, 255, 255, 0.35);
    }
    100% {
        box-shadow: 0px 0px 40px rgba(255, 255, 255, 0.5);
    }
}
```

Container styling:
```css
#container {
    box-shadow: 0px 0px 40px rgba(255, 255, 255, 0.5);
    -moz-animation: 'glow' 3s linear;
    -webkit-animation-name: 'glow';
    -webkit-animation-duration: 3s;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-timing-function: linear;
}
```
