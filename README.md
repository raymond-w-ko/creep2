# A proper copy of the 'creep' font by romeovs
## Original Here:
### https://github.com/romeovs/creep

I love romeovs's creep font, but I think you could only use it well in Apple's Terminal.app,
where one could have negative line and character width spacing. The root cause of this appears to 
be because some glyphs are outside the 5px by 11px bounding box, causing a boundings box calculation to take the max bounding 
box of largest glyph.

In order to accomplish this, I manually hand painted all the glyphs from the 'creep' font in fontforge.
This was probably not the smartest way, but I did not have time to research a method to change it by code.
On the plus side, I was watching a few movies while drawing these glyphs, so it wasn't too bad.

After doing this I could understand why some characters extended past the bounding box, as 5x11 is ridiculously small
for the more complicated fonts. However, to get it work nicely on terminals and editors without negative spacing support,
I had to use my best judgement and truncate or modify certain glpyhs so they all fit with no exceptions. This of course
is not as nice, and arguably makes certain glyphs much less recognizable, but I felt it was an acceptable compromise since
they do not appear often anyways.

### Result

By maintaining the strict 5x11 bounding box, I was able to get the font working in all the programs I typically use that don't support fancy spacing adjustment:
* XTerm (BDF format)
* UXRvt (BDF format)
* X11 (BDF format)
* Windows GVim (FON format export, name edited with Fony.exe to just "creep2" to fix bug in Windows?)
* mintty (same FON as above, but with LineSpacing=-1 in recent builds to fix hardcoded 1 pixel line offset).

Now I have crazy awesome code density :-)
