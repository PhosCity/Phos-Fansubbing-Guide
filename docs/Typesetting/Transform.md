# Transform

In all the tags that was introduced prior to this, there was always a note which
stated if the tag was transformable or not. Now we finally learn what
transforming a tag means.

Transform tag performs a gradual, animated transformation from one set of override
tags to another set. Only a limited set of the override tags can be animated by
the transform tags.

The tags that can be animated are:

| General | Color | Alpha   | Geometry | Clip    |
| ------- | ----- | ------- | -------- | ------- |
| \\bord  | \\c   | \\alpha | \\fs     | \\clip  |
| \\xbord | \\1c  | \\1a    | \\fscx   | \\iclip |
| \\ybord | \\2c  | \\2a    | \\fscy   |         |
| \\shad  | \\3c  | \\3a    | \\frx    |         |
| \\xshad | \\4c  | \\4a    | \\fry    |         |
| \\yshad |       |         | \\frz    |         |
| \\fsp   |       |         | \\fax    |         |
| \\blur  |       |         | \\fay    |         |

| Format                                            | Description                                                                           |
| ------------------------------------------------- | ------------------------------------------------------------------------------------- |
| \\t(_&lt;tags>_)                                  | Animate the value of override tags `<tags>`                                           |
| \\t(_&lt;accel>_,_&lt;tags>_)                     | Animate the override tags non-linearly using `accel` parameter                        |
| \\t(_&lt;t1>_,_&lt;t2>_,_&lt;tags>_)              | Animate the override tags from time `t1` to `t2`                                      |
| \\t(_&lt;t1>_,_&lt;t2>_,_&lt;accel>_,_&lt;tags>_) | Animate the override tags from time `t1` to `t2` non-linearly using `accel` parameter |

## t1 and t2

`t1` and `t2` parameters specify the time in milliseconds. These time are relative
to the start time of the line i.e. if t1 = 1000 means the transformation
starts 1000 milliseconds after the start of the line.

These times represents interval to perform the transformation over. In the version
without `t1` and `t2`, the transformation is performed over the entire duration of
the line.

Before `t1`, the appearance of the line is informed by the tag values before transform.
After `t2`, the appearance of the line is informed by the tag values in the transform
tag. Between `t1` and `t2`, the tag values are animated from the initial tag values
to the final tag values.

## Accel

The accel parameter can be used to make the animation non-linear and instead follow
an exponential curve.

$$
y = x \text{ with } x \in [0;1]  = \frac{t - t_1}{t_2 - t_1}
$$

t being the current time.

An _accel_ parameter of 1 causes the animation speed to be linear. A value between
0 and 1 causes the animation to start fast and end slow. A value greater than 1
causes the animation to start slow and end fast.

<h3>Example</h3>

```

{\1c&HFF0000&\t(\c&H0000FF&)}I am not amused

```

<video width="1920" height="1080" controls>
  <source src="../assets/Transform/transform_0.000-2.110_noaudio_1745329085729_0.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

```

{\1c&HFF0000&\t(500,1500,\c&H0000FF&)}I am not amused

```

<video width="1920" height="1080" controls>
  <source src="../assets/Transform/transform_2.110-5.110_noaudio_1745329794298_0.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

```

{\fscx0\fscy0\t(0,1000,\fscx100\fscy100)}I am not amused

```

<video width="1920" height="1080" controls>
  <source src="../assets/Transform/transform_5.110-8.110_noaudio_1745329998248_0.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

```

{\fscx0\fscy0\t(0,1000,0.5,\fscx100\fscy100)}I am not amused

```

<video width="1920" height="1080" controls>
  <source src="../assets/Transform/transform_8.110-11.110_noaudio_1745330018782_0.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

```

{\fscx0\fscy0\t(0,1000,4,\fscx100\fscy100)}I am not amused

```

<video width="1920" height="1080" controls>
  <source src="../assets/Transform/transform_11.120-14.120_noaudio_1745330048771_0.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

```

{\t(0,3000,\frz3600)}I am not amused

```

<video width="1920" height="1080" controls>
  <source src="../assets/Transform/transform_14.120-18.290_noaudio_1745330064770_0.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

```

{\t(0,3000,0.5,\frz3600)}I am not amused

```

<video width="1920" height="1080" controls>
  <source src="../assets/Transform/transform_18.290-22.460_noaudio_1745330079606_0.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

