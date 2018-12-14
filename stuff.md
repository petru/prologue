---
layout: page
title: Useful things
---

This is a list of _free_ and useful things on the net, along with quick fixes to peculiar problems.

### Tutorials & References
* [Learn to Code HTML & CSS](https://learn.shayhowe.com) by **Shay Howe** is a seemingly up-to-date resource. I use this to refresh my HTML5 and CSS3 knowledge.
* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) by **Adam Pritchard**

### Linux

* Unless you're using a wildly popular distro (Ubuntu, Fedora), your fonts probably don't look all that good. Fortunately, I've found a quick fix on [StackExchange](https://unix.stackexchange.com/a/226926). Create or replace the contents of your `~/.fonts.conf` with the following configuration:
```
    <?xml version='1.0'?>
    <!DOCTYPE fontconfig SYSTEM 'fonts.dtd'>
    <fontconfig>
        <match target="font">
            <edit mode="assign" name="rgba">
            <const>rgb</const>
        </edit>
        </match>
        <match target="font">
            <edit mode="assign" name="hinting">
                <bool>true</bool>
            </edit>
        </match>
        <match target="font">
            <edit mode="assign" name="hintstyle">
                <const>hintslight</const>
            </edit>
        </match>
        <match target="font">
            <edit mode="assign" name="antialias">
                <bool>true</bool>
            </edit>
        </match>
        <match target="font">
            <edit mode="assign" name="lcdfilter">
                <const>lcddefault</const>
            </edit>
        </match>
    </fontconfig>
```
    Don't forget to restart your browser and DE afterwards. I've successfully tested this on Slackware 14.2.
* Firefox won't play H.264-encoded video on Slacwkware 14.2 by default. Facebook and Netflix deliver video this way. There's an easy fix for this--either compile `ffmpeg` from Slackbuilds with `X264=yes` or use [AlienBob's package](http://www.slackware.com/~alien/slackbuilds/ffmpeg/pkg64/14.2/) which already has this enabled.