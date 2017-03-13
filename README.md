## My Library: racket/draw
My name: Brian Medina

I decided to use the draw library to make some pictures. First of all, I loaded up some sample code provided in the basic documentation for pict constructors:

![triangle](/1.png "triangle")

```racket
(require pict
    racket/draw)

(dc (λ (dc dx dy)
        (define old-brush (send dc get-brush))
        (define old-pen (send dc get-pen))
        (send dc set-brush
          (new brush% [style 'transparent]
                      [color "black"]))
        (send dc set-pen
          (new pen% [width 3] [color "black"]))
        (define path (new dc-path%))
        (send path move-to 0 0)
        (send path line-to 100 0)
        (send path line-to 50 100)
        (send path close)
        (send dc draw-path path dx dy)
        (send dc set-brush old-brush)
        (send dc set-pen old-pen))
    100 100)
```