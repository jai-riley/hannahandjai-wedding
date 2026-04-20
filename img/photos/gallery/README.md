# Gallery Photos

This folder contains the photos shown in the **Photos** section of the site.

## How to add your photos

Each photo needs two versions:
- `photo-01-sm.jpg` — small thumbnail shown in the grid (~400×300px, under 100 KB)
- `photo-01-lg.jpg` — full resolution shown when clicked (~1200×900px)

Name them sequentially: `photo-01`, `photo-02`, `photo-03`, etc.

## How to wire them up in index.html

Find the `#eng-pics` section in `index.html`. Each photo block looks like this:

```html
<div class="col-md-2">
    <a class="fancybox" rel="group" href="img/photos/gallery/photo-01-lg.jpg">
        <div class="img-wrap">
            <div class="overlay"><i class="fa fa-search"></i></div>
            <img src="img/photos/gallery/photo-01-sm.jpg" alt="Hannah and Jai"/>
        </div>
    </a>
</div>
```

Add or remove `<div class="col-md-2">` blocks to match the number of photos you have.
The grid fits **6 per row** (col-md-2 × 6 = 12 columns). Add a new `<div class="row">` for each additional row of 6.
