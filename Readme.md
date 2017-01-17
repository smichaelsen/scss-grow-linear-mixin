# Sass mixin: `grow-linear`

## Basic usage

This mixin is useful if you want to define certain CSS values (like `font-size`) for certain breakpoints and want them
to grow linearly in between.

    h1 {
        $font-sizes: (
            320 20,
            640 30,
        );
        @include grow-linear(font-size, $font-sizes);
    }
    
This will make your `<h1>` font-size 20px at a viewport width of 320px (and below) and 30px at 640px viewport width (and
above). Between those viewport widths the font-size grows linearly - so it will be 25px at 480 viewport widths.

## Named sizes

When you have layout files for certain screen sizes that you need to implement it can be useful to use *named sizes*.

    $sizes: (
        phone: 320,
        portrait: 768,
        landscape: 1024,
        desktop: 1440,
    )
    
    h1 {
        $font-sizes: (
            phone 20,
            portrait 30,
        );
        @include grow-linear(font-size, $font-sizes);
    }

## Credits

The logic of growing values linearly with the screen size is inspired by this video by Daniel Diekmeier

[![CSS: Interpolation, lineare Gleichungen und calc](https://img.youtube.com/vi/NeQrOPRqtr4/0.jpg)](https://www.youtube.com/watch?v=NeQrOPRqtr4)
