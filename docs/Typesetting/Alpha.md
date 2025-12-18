# Alpha

Set the alpha (transparency) of the text. An alpha of `00` (0 in decimal) means
opaque and an alpha of `FF` (255 in decimal) is fully transparent.

!!! note

    You will not be typing the hexadecimal parameter yourself. So don't go out
    lerning it right now.

| Format            | Description                                                                |
| ----------------- | -------------------------------------------------------------------------- |
| \\alpha&H&lt;aa>& | Alpha for the whole text                                                   |
| \\1a&H&lt;aa>&    | Alpha for the fill of the text only                                        |
| \\2a&H&lt;aa>&    | Alpha for the fill of the text for karaoke (Rarely useful for typesetting) |
| \\3a&H&lt;aa>&    | Alpha for the border of the text only                                      |
| \\4a&H&lt;aa>&    | Alpha for the shadow of the text only                                      |

<h3>Example</h3>

| Example      | Description                                                                                           |
| ------------ | ----------------------------------------------------------------------------------------------------- |
| \\alpha&H80& | Set the alpha of all components to hexadecimal 80 (decimal 128) making the whole text 50% transparent |
| \\1a&HFF&    | Set the alpha of fill to hexadecimal FF (decimal 255) making the fill of text 100% transparent        |

```

{\alpha&H00&}I am {\alpha&HFF&}not{\alpha&H00&} amused.

```

![alpha](./assets/Alpha/alpha.png)

```

{\bord3\shad0\1a&H00&}I am {\1a&HA8&}not {\1a&HFF&}amused.

```

![1a](./assets/Alpha/1a.png)

```

{\bord3\shad5\4a&H00&}I am {\4a&HA8&}not {\4a&H53&}amused.

```

![4a](./assets/Alpha/4a.png)

## Adding alpha

You can obviously type out the `alpha` tag yourself but you can also use the
color picker to add alpha.

![color picker alpha](./assets/Alpha/color_picker_alpha.svg)

In the image above, you will notice that there is a box where you can type the
alpha in decimal from 0 (opaque) to 255 (transparent). You can type the number
there and click `OK` to add alpha.

However, you will also notice that there is a slider where the top represents
opaque text and bottom represents transparent text. You can click anywhere in
the slider or drag the slider to the desired point to apply the required
transparency.

You will remember that there are four color pickers in the `Edit box`. You can
use those to selectively add alpha to fill, border and shadow.

<video width="2254" height="1386" controls>
  <source src="../assets/Alpha/1a.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

