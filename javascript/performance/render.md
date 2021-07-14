# Render Performance

## Web Page creation

- Browser requests webpage from a server
- Gets back HTML
- Parsed HTML into DOM - representation of a webpage

    ### DOM

    Representation of a webpage

- Fetches CSS
- Parses CSS into CCSOM

    ### CCSOM

    Tree of css rules.

- joins DOM and CCSOM into Render Tree - representation of whats gonna show on the webpage

    ### Render Tree
    Here's what's gonna be visible, this is how it should look 
    - one to one mapping with visible objects on the page
    - no idden objects
    - pseudo elements
    - figure out which rules apply to the element, uses style calculation

    ### Style calculation
    - figure out which rules apply to which elements
    - figure out rules specifity
    - prefer simple classes
    - the less selectors the faster

- Layout - look at the page and figure out where they go on page
- Paint - draw pixels on the screen
- Composite Layers
- JavaScript -> Style -> Layout -> Paint -> Composite

## Layouts

- Reflows are very expensive.
- Has to happen whenever dimensions change.
- It's a blocking operation.
- Consumes decent amount of CPU.
- Noticable for users if it happens often.
- Reflow of an element causes a reflow of its parents and children -> most of the time reflow of the whole application.

Then you have to repaint, which is also expensive.

### How to avoid

- Change classes at the lowest levels of the DOM tree.
- Avoid repeatedly modifying inline styles.
- Trade smoothness for speed with animation in JS.
- Avoid table layouts.
- Batch DOM manipulation (frameworks ftw).
- Debounce window resize events.

### Layout Thrashing

Occurs when JS violently writes, then reads, from the DOM, mutliple times causing document reflows.

Every time you measure if something changed since last time we measured it needs to reflow.

_Note_: Seperate reading from writing.


- requestAnimationFrame - meh
- FastDOM - small library that batches measures and mutations of DOM
- Frameworks - pretty good

## Paint

- Any change other than opacity or CSS transform triggers paint.
- Browser tells every element on the page to draw a picture of itself.

### Compositor Thread


GPU intensive thread. We should offload stuff to it as much as possible. You can do that by managing layers.

Good at:

- redrawing bitmaps
- scaling and rotating bitmaps
- making bitmans transparent
- applyling filters
- mining crypto c:

### Managing Layers

`will-change` will recommend browser to make something its own layer.
