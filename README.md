# lesscss-mixins

Collection of common lesscss mixins to create cross browser css3 rules.
[github.com/activeids/lesscss-mixins](https://github.com/ActiveIDs/lesscss-mixins)

## aim
CSS3 brings web style rules to the next level with border radius, background gradients, box and text shadows, transformations and even animations. The downside is that it's not (yet) supported by every browser and each browser often has its own notation. Writing the style rules for each browser is tedious. Enter [LessCss](http://lesscss.org): extending CSS with dynamic behavior such as variables, mixins, operations and functions. Using Less we can create smart code blocks unifying the style notation and letting the CSS be generated automatically. And for those (old) browsers that don't support CSS3 we'll add a sniff of [CSS3Pie](http://css3pie.com/).

## contents
This collection provides a set of reusable Less code blocks for common CSS3 styles such as opacity, rgba & gradient backgrounds, rounded corners, box & text shadows, transformations, animations and other common mixins. Some of the original cross browser CSS rules are inspired by [CSS3, please](http://css3please.com/) and some of the Less code blocks are borrowed from [nettuts+](http://net.tutsplus.com/tutorials/php/how-to-squeeze-the-most-out-of-less/).

## example
A box shadow mixin from _shadows.less:

    .boxShadow(@x, @y, @blur, @radius, @color)
    {
        @box-shadow: @x @y @blur @radius @color;

           -moz-box-shadow: @box-shadow;
        -webkit-box-shadow: @box-shadow;
                box-shadow: @box-shadow;
    }

Can simply be used as:

    .mySelector {
        .boxShadow(2px, 3px, 3px, 1px, #666);
        /* other declarationss */
    }

And will result in a cross browser box shadow:

    .mySelector {
           -moz-box-shadow: 2px 3px 3px 1px #666;
        -webkit-box-shadow: 2px 3px 3px 1px #666;
                box-shadow: 2px 3px 3px 1px #666;
        /* other declarationss */
    }