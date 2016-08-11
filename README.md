Check it out here: https://ugotsta.github.io/eerie-css/

# Eerie CSS

Dead simple, this is just an HTML page with some CSS to achieve a sort of shaky, old film effect. It's somewhat like the flickering effect seen in games like Limbo (http://store.steampowered.com/app/48000/), done solely with CSS styling and animations.

Some other elements have been added for effect, such as fonts and hover effects.

Example of CSS in use here:
http://hid.ugotsta.com/

## What's involved

The page is composed of simple HTML and some CSS3 stlying and animations. No JavaScript is involved.

### Flickering background

The background flicker is achieved using a CSS animation on a div with absolute positioning and with a soft, radial gradient for the background. The div is given an id of 'shakewrap'. The animation is just a simple rotate transform.

Flicker Animation:
```css
@keyframes bigshakes {
    0% {
        transform: translate(2px, -8px) rotate(-1deg);
    }
    50% {
        transform: translate(-9px, 10px) rotate(-18deg);
    }
    100% {
        transform: translate(6px, -2px) rotate(1deg);
    }
}
```

Shakewrap styling:
```css
#shakewrap {
    z-index: 1;
    pointer-events: none;
    height: 100vmax;
    width: 120%;
    position: fixed;
    top: -20px;
    left: -20px;
    animation: bigshakes 0.1s linear infinite;
    opacity: 0.5;
    background-color: #111;
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 65%, rgba(0, 0, 0, 1) 100%);
}
```

### Shaky hover effect

Anchor links are given a subtle shake effect when hovered over, again using a CSS animation.

Shake animation:
```css
@keyframes shakes {
    0% {
        transform: translate(2px, 1px) rotate(1deg);
    }
    50% {
        transform: translate(-1px, 1px) rotate(0deg);
    }
    100% {
        transform: translate(1px, -2px) rotate(0deg);
    }
}
```

Hover styling:
```css
a:hover {
    text-shadow: 0px 0px 18px rgba(255, 0, 0, 1);
    animation: shakes 0.1s linear infinite;
}
```

### Glow effect

A subtle glow effect is used for the container div wrapping the text. It relies on a simple transition which is then applied in the container's styling.

Glow animation:
```css
@keyframes glow {
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

Container styling for glow effect:
```css
#container {
    box-shadow: 0px 0px 40px rgba(255, 255, 255, 0.5);
    animation: glow 3s linear infinite;
}
```
