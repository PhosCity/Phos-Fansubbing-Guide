# Applying Fade

We have learned about fade previously but we only learned about the tag. Now let
us actually learn how we apply fade in a real sign. As you might have guessed by
now, we also use an Aegisub script to add fade to the line.

## Fadeworks

Fadeworks is the script made by unanimated whose purpose is to add fades as well
as some other fading effects. So install it from dependency control and
immediately bind it to a hotkey. I bind it to key `F` in subtitle grid.

Let us take a following example and see how we use the script `Fadeworks` to
apply fade to this line.

<figure>
    <video width="1440" height="1080" controls>
        <source src="../assets/Applying Fade/fade_example.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <figcaption><a href="https://onepace.net">One Pace</a> - Drum Island Episode 05: 0:05:51.46 </figcaption>
</figure>

1. The line must be timed such that it starts in the same frame as the text
   begins to appear and ends in the same frame as the text completely disappears.
1. In the `Video Box`, go to the first frame of the line if it isn't already.
   Hotkey is ++ctrl+1++ if you forgot.
1. Then press ++arrow-right++ to step forward through each frame of video
   until the text fully appears.
1. Enable the subtitle grid by clicking in the line you are trying to apply fade
   to and press the hotkey to run `Fadeworks`.
1. Enable the checkbox `Fade in to current frame` and press `Apply Fade` button.
   This will add fade tag to line but only fade in.
1. Then go to the last frame of the line. ++ctrl+2++ is the hotkey.
1. Then press ++arrow-left++ to step backward through each frame of video
   until the text fully appears.
1. Run the `Fadeworks` script again. This time enable the checkbox `Fade out
   from current frame` and press `Apply Fade` button. This will add fade tag
   with fade out but doesn't change the fade in tag.

<video width="2560" height="1544" controls>
    <source src="../assets/Applying Fade/fadeworks_example.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

If you already know the fade in time and fade out time in milliseconds, you can
directly input the values in `Fadeworks` and `Edit Tags` script

=== "Fadeworks"

    <video width="2560" height="1544" controls>
        <source src="../assets/Applying Fade/fadeworks_input.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

=== "Edit Tags"

    <video width="2560" height="1542" controls>
        <source src="../assets/Applying Fade/edit_tags_input.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

## AutoFade

AutoFade is an Aegisub script written by me to automate the process of applying
fade so that you don't have to step through the frames to find the exact
frame/time when the text fades in or fades out. So get it from Dependency Control.

!!! note

    This is an alternative to `Fadeworks` example shown above. Use this method
    or the other based on what works for you. Even if you use this method for
    adding fades, I still recommend you to keep `Fadeworks` around. It's a useful
    script.

1. Time your sign.
1. Determine if your sign has fade in, fade out or both.
1. Play the video until you reach any frame in which there is neither fade in nor
   fade out.
1. Hover over the Japanese sign, right click and choose "Copy coordinates to Clipboard".
1. Open the script (while staying in the same video frame). The co-ordinate should
   have automatically be picked up and shown in the GUI. Then choose Fade in or Fade
   out or Both button depending on what you want.
1. The script will automatically add appropriate fade to your text.

<video width="2560" height="1546" controls>
    <source src="../assets/Applying Fade/autofade.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

## Fade to/from Color

<figure>
    <video width="1920" height="1080" controls>
        <source src="../assets/Applying Fade/fade_from_color.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <figcaption><a href="https://anilist.co/anime/155419/Hoshikuzu-Telepath/">Hoshikuzu Telepath</a> - Episode 03: 0:00:02 </figcaption>
</figure>

Sometimes we will get signs like this where instead of fading to/from
transparency, the sign will fade to/from color. Here, every part of the sign is
black at the beginning and is slowly fading to it's original color.

Every step is just like before, but before hitting `Apply Fade` button, we
enable the checkbox that says `From:` and then select color to fade from that
color. However, if the text fades to a certain color, choose `To:` and select
this color.

<video width="2560" height="1554" controls>
    <source src="../assets/Applying Fade/fade_from_color_result.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

Even though the start color was pitch black, I sampled color from the first frame
as an example. You can notice that both the black text, blue text and the white
border all start from black and fade into their original color. In case you are
keeping track of what automation scripts are doing like I told you, it's using
`\t` tag to animate the color.


## Letter by Letter

<figure>
    <video width="1920" height="1080" controls>
        <source src="../assets/Applying Fade/fadeworks_letter_by_letter_example.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <figcaption><a href="https://anilist.co/anime/112667/Kimi-to-Boku-no-Saigo-no-Senjo-Arui-wa-Sekai-ga-Hajimaru-Seisen/">Kimi to Boku no Saigo no Senjo, Arui wa Sekai ga Hajimaru Seisen </a> - Episode 01: 0:22:17 </figcaption>
</figure>

<video width="2560" height="1540" controls>
    <source src="../assets/Applying Fade/fadeworks_letter_by_letter.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

As you can see there is much work to be done in this sign but this is how you apply
letter by letter using `Fadeworks`.

In the GUI of `Fadeworks`, you will also find a checkbox called `Letter by letter
using \ko`. If you tick this and press `Letter by Letter` button, the effect will
be slightly different.

<video width="1300" height="350" controls>
    <source src="../assets/Applying Fade/fadeworks_letter_by_letter_alpha_ko.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>

The top one is when `Letter by letter using \ko` is enabled and bottom is when it
is not. Do yo notice the difference? The top one appears abruptly like a letter
stamped by a typewriter. The bottom one gradually fades into existence.
