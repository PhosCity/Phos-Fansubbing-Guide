# Fade

Fade in refers to the effect where a text starts as transparent and later turns opaque.

Fade out refers to the effect where a text starts as opaque turns transparent.

!!! note

    Adding a fade effect does not extend the duration of the line. Instead the
    effect is visible within the duration of line.

## Simple Fade

!!! note ""

    Global / Untransformable Tag

Performs a two part fade effect: fade in at the start of line and fadeout at the
end of the line.

| Format                         | Description                                               |
| ------------------------------ | --------------------------------------------------------- |
| \fad(&lt;fadein>,&lt;fadeout>) | Fade in effect at `<fadein>` and `<fadeout>` milliseconds |

<h3>Example</h3>

```

{\fad(1200,250)}

```

<video width="1920" height="1080" controls>
  <source src="../assets/Fade/fade.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

## Complex Fade

!!! note ""

    Global / Untransformable Tag

!!! info

    I have never used complex fade ever. You'll probably never use it too. I've just put it here for completness.

Perform a five-part fade using three alpha values `a1`, `a2`, `a3` and four time
values `t1`, `t2`, `t3` and `t4` where time value is in milliseconds and alpha
is in the decimal format (0-255).

1. Before `t1`, the line has alpha `a1`.
1. Between `t1` and `t2`, line fades from alpha `a1` to alpha `a2`.
1. Between `t2` and `t3`, the line has alpha `a2` constantly.
1. Between`t3` and `t4`, the line fades from alpha `a2` to `a3`.
1. After `t4`, the line has alpha `a3`.

<h3>Example</h3>

```

\fade(255,32,224,0,500,2000,2200)

```

<video width="1920" height="1080" controls>
  <source src="../assets/Fade/fade_complex.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

## How to find `t1` and `t2`

You need to find the time to put it in the fade tag. Do you remember we learned
about subs relative time in the video box page? I told you it will become useful
later on too, didn't I? This is the time.

<!-- TODO: Link the video box page -->

Let's say we want to find the time for fade in. The text is transparent in the
beginning. You start from the first frame of the text
(_Press ++ctrl+1++ in video box_) and step through the video frame forward
with right arrow key until the text becomes fully opaque. You look at
the start relative time in milliseconds. That is your fade in time.

Let's try to do the fade out time. The text is transparent at the end. You go
the end frame of the text (_Press ++ctrl+2++ in video box_), step through the
video frame backwards using left arrow key until the
text becomes fully opaque. You look at the end relative time in milliseconds.
That is your fade out time.
