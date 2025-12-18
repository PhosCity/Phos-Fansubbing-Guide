# Move

!!! note ""

    Global / Untransformable Tag

The tag `\move` works similar to the tag `\pos` in that it positions the subtitle
line. The difference is that it also makes the subtitle move linearly. Move cannot
perform non-constant speed movement. For example, movement cannot start out slow
and end fast. Non linear movement will be discussed later in this guide.

!!! note

    Alignment influences movement coordinates the same way it influences `\pos` coordinates.

!!! warning

    There can only be either `\pos` tag or `\move` tag in a line. There can also
    not be more than one move tags in a line.

There are two versions of move.

## Version 1

```

\move(<x1>,<y1>,<x2>,<y2>)

```

The line starts out at point `(x1, y1)` and moves with constant speed. So it ends
up at `(x2, y2)` at the end of the line's duration.

<video width="1920" height="1080" controls>
  <source src="../assets/Move/move.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

## Version 2

```

\move(<x1>,<y1>,<x2>,<y2>,<t1>,<t2>)

```

Here, `t1` and `t2` and time in milliseconds. They are derived same way you did
for fade tag.

<video width="1920" height="1080" controls>
  <source src="../assets/Move/move_(complex).mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

## t1 and t2

`t1` and `t2` are time in milliseconds. It is legal to have `t1` and `t2` specify
times greater than the duration of the line. When both `t1` and `t2` is 0, it is
the same as using version 1 of move i.e. `\move(x1, y1, x2, y2, 0, 0)` is same as
`\move(x1, y1, x2, y2)`

## Adding Move Tag

I don't know if you notice but `Drag` tool has a sub-tool. We can use it to add
move tag to the line.

1. Enable `Drag` mode in the video box. Then we enable the sub-tool.
1. We start from the first frame of the line. From that frame, we step through
   frame forward or play the video until we reach the frame where the movement
   ends. (_Yes we set the end first_)
1. In that frame, we drag the circular anchor to the desired location.
1. Then we start from the first frame again. We step through video frames until
   we reach the frame where the movement starts.
1. In that frame, drag the square anchor to the position from which the movement
   starts.
1. Of course, if your move starts on first frame and last until the last frame,
   then you just have to set the position of text in first frame, go to the last
   frame of the video (_Press ++ctrl+2++ in Video Box_) and drag the circular
   anchor to the desired position.

<video width="1910" height="1216" controls>
  <source src="../assets/Move/move_tool.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

