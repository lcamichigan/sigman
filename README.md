# Sigman

[![Build status](https://ci.appveyor.com/api/projects/status/91u8bs1bmmv0jwn4?svg=true)](https://ci.appveyor.com/project/lcamichigan/sigman)

This is a collection of resources for creating issues of _The Sigman_, the
newsletter of [Sigma Zeta of ΛΧΑ](https://lcamichigan.com).

## Contents

* [Getting Started](#getting-started)
* [Preparing an Issue](#preparing-an-issue)
  * [Calendar](#calendar)
  * [Donor Honor Roll](#donor-honor-roll)
  * [Lost Brothers](#lost-brothers)
* [Converting Raster Images of Signatures to Vector Images](#converting-raster-images-of-signatures-to-vector-images)
  * [On Windows](#on-windows)
  * [On macOS](#on-macos)
* [Guidelines for Articles](#guidelines-for-articles)
* [Guidelines for Photos](#guidelines-for-photos)
* [Creating a Thumbnail](#creating-a-thumbnail)
  * [On Windows](#on-windows-1)
  * [On macOS](#on-macos-1)
* [About _The Sigman_ Template](#about-the-sigman-template)
* [About the Envelope](#about-the-envelope)

## Getting Started

To create an issue of _The Sigman_, you need:

* [Adobe InDesign](https://www.adobe.com/products/indesign.html). Visit
https://www.adobe.com/creativecloud/plans.html for more information.

* Envelope.idml and Sigman.idml. The easiest way to get these files is to
download them from
https://ci.appveyor.com/project/lcamichigan/sigman/build/artifacts, but you can
also [create your own](https://github.com/lcamichigan/make-idml).

* These fonts:

    | Font                                                                     | Download URL                                                             |
    |--------------------------------------------------------------------------|--------------------------------------------------------------------------|
    | [Arvo](https://fonts.google.com/specimen/Arvo)                           | https://github.com/google/fonts/raw/master/ofl/arvo/Arvo-Regular.ttf     |
    | [Damion](https://fonts.google.com/specimen/Damion)                       | https://github.com/google/fonts/raw/master/ofl/damion/Damion-Regular.ttf |
    | [Gillius](http://arkandis.tuxfamily.org/adffonts.html)                   | http://arkandis.tuxfamily.org/fonts/Gillius-Collection-20110312.zip      |
    | [League Spartan](https://www.theleagueofmoveabletype.com/league-spartan) | https://github.com/theleagueof/league-spartan/archive/master.zip         |
    | [Libertinus](https://github.com/libertinus-fonts/libertinus)             | https://github.com/libertinus-fonts/libertinus/releases/latest           |

## Preparing an Issue

### Calendar

Here is where you can find dates of events to include in the calendar:

| For these kinds of events | Visit                             |
|---------------------------|-----------------------------------|
| U‑M academics             | https://ro.umich.edu/calendars    |
| U‑M sports                | https://mgoblue.com               |
| ΛΧΑ                       | https://www.lambdachi.org/events/ |

### Donor Honor Roll

Updating the Honor Roll requires access to the Sigma Zeta Address List on Google
Drive.

To update the Honor Roll:

1. View the Filtered Donations sheet of the Sigma Zeta Address List. Cell A2 of
this sheet contains a
[`FILTER`](https://support.google.com/docs/answer/3093197). Change the `FILTER`
so that it has two conditions, one for the earliest date of donations, for
example:

    ```
    Donations!A:A >= DATEVALUE("1/1/2017")
    ```

    and one for the latest date of donations, for example:

    ```
    Donations!A:A < DATEVALUE("1/1/2018")
    ```

2. View the Honor Roll sheet. In the last four columns, select cells that have
the same Category, and then press Ctrl-C to copy the selection. In InDesign,
paste the selection (press Ctrl-V to paste) into the appropriate category.
(Class years of donors will probably break onto a new line. Don’t worry about
this for now.) Repeat this for each category.

3. Replace tab characters before class years with non-breaking spaces. To do
this:

    1. Choose Edit > Find/Change (or press Ctrl-F) to show the Find/Change
    dialog, and then click the GREP tab.

    2. In the “Find what” field, enter `\t(?=’\d\d$)`. This finds tab characters
    (`\t`) that are followed by a right single quotation mark (`’`) and two
    digits (`\d`) at the end of a line (`$`).

    3. In the “Change to” field, enter `~S`, which means a non-breaking space.

    4. Choose Story from the Search menu, and then click Change All.

    After you do this, some class years may still appear on lines by themselves.
To fix this, delete middle initials of long names. You can also decrease
[tracking](https://en.wikipedia.org/wiki/Letter-spacing) (press Alt–Left Arrow)
of names and class years.

The Honor Roll is in a 3-column text frame, with columns 106 pt wide and 1 pt
gutters. If there are many donations, the Honor Roll can also be in a 4-column
text frame, with columns 129 pt wide and 8 pt gutters.

### Lost Brothers

Updating the list of lost brothers requires access to the Sigma Zeta Address
List on Google Drive.

To update the list of lost brothers:

1. View the Lost Alumni sheet of the Sigma Zeta Address List. Excluding the
header row, select the sheet, and then press Ctrl-C to copy the selection. In
InDesign, paste the selection (press Ctrl-V to paste) into the list of lost
brothers. If the character style is wrong (for example, if the pasted text is
bold), press Ctrl-A to select the entire lost brother section, choose Type >
Paragraph Styles, and then click the Clear Overrides button (looks like ¶\*).

2. Add tab characters before the Sigma number of each lost brother. To do this:

    1. Choose Edit > Find/Change (or press Ctrl-F) to show the Find/Change
    dialog, and then click the GREP tab.

    2. In the “Find what” field, enter `^(.)`. This finds the beginning of a
    line (`^`) followed by any character (`.`). (Finding any character is a
    workaround for the fact that finding the beginning of a line doesn’t appear
    to work on its own.)

    3. In the “Change to” field, enter `\t$1`, which means a tab character
    (`\t`) followed by the character found at the beginning of the line (`$1`).

    4. Choose Selection from the Search menu, and then click Change All.

3. Abbreviate and format class years. To do this:

    1. Choose Edit > Find/Change (or press Ctrl-F) to show the Find/Change
    dialog, and then click the GREP tab.

    2. In the “Find what” field, enter `\t\d\d(\d\d)$`. This finds tab
    characters (`\t`) followed by four digits (`\d`) at the end of a line (`$`).

    3. In the “Change to” field, enter `~S’$1`. This replaces text with a
    non-breaking space (`~S`), a right single quotation mark (`’`), and the two
    digits found at the end of the line (`$1`).

    4. Click the Change Format box to show the Change Format Settings dialog,
    choose Lost Brother Class Year from the Character Style menu, and then click
    OK.

    5. Choose Selection from the Search menu, and then click Change All.

If there are too many lost brothers to fit the text frame, delete brothers with
the lowest Sigma numbers.

Some class years may appear on lines by themselves. To fix this, delete middle
initials of long names.

To count lost brothers, select all of them, and then choose Windows > Info or
press F8. The number of paragraphs is the number of lost brothers.

## Converting Raster Images of Signatures to Vector Images

In general, signatures for High Alpha letters must be converted from raster
images to vector images. The easiest way to do this is probably using
[Potrace](http://potrace.sourceforge.net). Once you install Potrace, you can
create a PDF file from an image named Signature.bmp by entering in PowerShell,
Command Prompt, or Terminal:

```
potrace --backend pdf --output Signature.pdf --tight Signature.bmp
```

### On Windows

To install Potrace on Windows, download a Windows distribution from
http://potrace.sourceforge.net/#downloading and follow the instructions in
http://potrace.sourceforge.net/README-WIN.

### On macOS

[Homebrew]: https://brew.sh

The easiest way to install Potrace is probably through [Homebrew]. To install
Homebrew, follow the instructions at https://brew.sh. After you install
Homebrew, enter in Terminal `brew install potrace`.

## Guidelines for Articles

Unless you’re the chapter president writing the High Alpha letter, or the alumni
advisor writing the occasional High Pi letter, you’re not writing a letter;
you’re writing a news article. A news article must, at minimum, tell your reader
the _who_, _what_, _when_, and _where_ of your topic. List names of people who
attended and planned events; if you don’t have a complete list, include a
partial list. State official names of events, their dates and times, and their
locations.

Don’t write fluff. Fluff is word salad that contributes nothing to your writing.
The sentence “Brothers also continue to be engaged as well” is fluff. An article
that tells a story in 200 focused words is preferable to an article that tells
the same story in 1,000 fluff-ridden ones.

Put the most important information about your topic in your article’s first
paragraph. In subsequent paragraphs, go into progressively more (but less
important) detail. For example, if you’re writing a semester-end review of
philanthropy, the first paragraph might contain the semester’s total number of
philanthropy events and what was raised by those events. Subsequent paragraphs
might describe particular events. If you’re writing about recruitment, the first
paragraph might contain the number of new members and their names. Subsequent
paragraphs might describe particular recruitment events and new member
programming.

Here are additional guidelines to keep in mind:

* Don’t type more than one space character after a period.

* Don’t type a tab at the start of a paragraph.

* Paragraphs should be preceded by a single paragraph break; press Enter _once_
to start new paragraphs.

* Use a right single quotation mark (’), not a straight single quotation mark
(') or a left single quotation mark (‘), to abbreviate a year.

    _Correct:_ George Spasyk ’49

    _Incorrect:_ George Spasyk ‘49

    Note that Microsoft Word’s “smart quotes” feature often uses the wrong
quotation mark in this case.

* Use _italics_ for emphasis, not bold or underlining.

* If you’re not writing a High Alpha or High Pi letter, avoid writing in the
first person. If you need to refer to yourself in an article, use _this writer_
or _this author_ instead of _me_ or _I_. Use _Sigma_ or _the collegiate
brothers_ instead of _we_ or _us_.

* Except when using _Sigma_ to refer to the chapter, avoid spelling out letters
of the Greek alphabet:

    Α Β Γ Δ Ε Ζ Η Θ Ι Κ Λ Μ Ν Ξ Ο Π Ρ Σ Τ Υ Φ Χ Ψ Ω

    Use _ΛΧΑ_ instead of _Lambda Chi Alpha_, and _ZAX_ instead of _Zeta Alpha
Chi_. Write Greek-letter fraternity names like _ΑΔΠ_, not _ADPi_. It’s OK to
abbreviate _ΛΧΑ_ as _ΛΧ_ and to refer to a group of Fraternity members as
_ΛΧs_.

* Use precise numbers. $1,001 and $1,000,000 are both “more than $1,000”.

* Don’t use _AM_ to abbreviate _associate member_.

* _Associate member_ and _brother_ should be capitalized only when used as
titles, for example, “The meeting was chaired by Brother George Spasyk ’49.
George is a brother from Sigma.”

* Don’t use _rushees_ to refer to _prospective members_.

* Don’t describe something as _historic_ or _momentous_ unless it is. Sigma’s
100th anniversary was historic. Having a formal dance go off without a hitch
is excellent, but not historic.

* Don’t capitalize seasons like _fall_ and _winter_.

* Don’t use _the house_ to refer to _the chapter house_.

* Use _Sigma_ instead of _Sigma Zeta_ and _Sigma Zeta of ΛΧΑ_.

* Use _U‑M_ or _Michigan_ when _University of Michigan_ is too verbose. Don’t
use _U of M_.

* Follow _Interfraternity Council_ with its initialism in parentheses (IFC) on
first use, and then use the initialism only. Unless you’re writing about more
than one Interfraternity Council, there’s no need to precede _IFC_ with
_Michigan_ or _U‑M_. Don’t hyphenate _Interfraternity_.

## Guidelines for Photos

* If you’re unfamiliar with photographic composition, learn the
[basics](https://lifehacker.com/5814174/basics-of-photography-composition-and-technique),
especially the [rule of thirds](https://en.wikipedia.org/wiki/Rule_of_thirds)
and [headroom](https://en.wikipedia.org/wiki/Headroom_(photographic_framing)). If
your camera or phone can superimpose a grid over its viewfinder or screen, turn
it on. In iOS 11 and later, you can turn on a grid in Settings > Camera.

* Don’t use digital zoom. (On iPhones, for example, you can use pinch gestures
to digitally zoom in; don’t do this.)

* Because _The Sigman_ is usually 4 pages, very often just one photo of an event
can be published. Remember to take photos that can summarize an event.

* Use common sense. Don’t photograph people chewing food. Keep trash bins and
anything resembling an alcoholic beverage out of the frame. Keep turned-on
televisions out of the frame unless a television is integral to the event (as at
an away game viewing party or a video game tournament).

* Prefer photos of Sigma members, especially photos of collegiate and alumni
members together. Avoid taking photos that contain neither people nor the
chapter house.

* When photographing a group of people in conversation, place as many faces in
the frame as possible.

* Prefer candid to posed photos, but when posing people for a photo, ask people
to remove name tags.

* Make sure you can identify everyone in your photos. If you use an iPhone, the
[Notes](https://support.apple.com/en-us/ht205773) app is a convenient way to
keep track of names.

## Creating a Thumbnail

Thumbnails of issues of _The Sigman_ are shown in a Squarespace
[gallery](https://support.squarespace.com/hc/en-us/articles/206543407) at
https://lcamichigan.com/newsletter. One way to make a thumbnail from a PDF file
is to use [ImageMagick](https://imagemagick.org).

### On Windows

The easiest way to install ImageMagick is probably through
[Chocolatey](https://chocolatey.org). To install Chocolatey, follow the
instructions at https://chocolatey.org/install. After you install Chocolatey,
enter in PowerShell or Command Prompt:

```
choco install ghostscript.app imagemagick.tool
```

To create a thumbnail, enter in PowerShell:

```powershell
magick convert --% -trim -colorspace sRGB -thumbnail 300x -crop 300x300+0+0 "File path.pdf"[0] "File path.png"
```

or in Command Prompt:

```batch
magick convert -trim -colorspace sRGB -thumbnail 300x -crop 300x300+0+0 "File path.pdf"[0] "File path.png"
```

### On macOS

The easiest way to install ImageMagick is probably through [Homebrew]. To
install Homebrew, follow the instructions at https://brew.sh. After you install
Homebrew, enter in Terminal `brew install imagemagick`.

To create a thumbnail, enter in Terminal:

```sh
convert -trim -colorspace sRGB -thumbnail 300x -crop 300x300+0+0 'File path.pdf'[0] 'File path.png'
```

## About _The Sigman_ Template

_The Sigman_ template is based on issues of _The Sigman_ from 1939–46 (available
at https://lcamichigan.com/newsletter). The
[nameplate](https://en.wikipedia.org/wiki/Nameplate_(publishing)) of these
issues appears to be set in a form of
[Caslon](https://en.wikipedia.org/wiki/Caslon) that’s similar to
[Big Caslon](https://store.typenetwork.com/foundry/cartercone/fonts/big-caslon/regular).
Body text appears to be a form of
[Century](https://en.wikipedia.org/wiki/Century_type_family). Headlines use a
variety of typefaces: [Bodoni](https://en.wikipedia.org/wiki/Bodoni),
[Caslon](https://en.wikipedia.org/wiki/Caslon),
[Kaufmann](https://en.wikipedia.org/wiki/Kaufmann_(typeface)),
[Memphis](https://en.wikipedia.org/wiki/Memphis_(typeface)), and either
[Metro No. 2](https://en.wikipedia.org/wiki/Metro_(typeface)) or
[Spartan](https://en.wikipedia.org/wiki/Spartan_(typeface)).

The nameplate in the template uses Big Caslon Medium (the version included with
macOS High Sierra 10.13) at 48 pt with tracking at 200 thousandths of an em.

Here are the fonts used in place of the originals:

| This font                                                                | is used in place of |
|--------------------------------------------------------------------------|---------------------|
| [Arvo](https://fonts.google.com/specimen/Arvo)                           | Memphis             |
| [Damion](https://fonts.google.com/specimen/Damion)                       | Kaufmann            |
| [League Spartan](https://www.theleagueofmoveabletype.com/league-spartan) | Spartan             |

## About the Envelope

The envelope includes an embedded image of a cross and crescent created using a
[cross-and-crescent package](https://github.com/lcamichigan/cross-and-crescent)
in LaTeX. To create this image,
[install](https://github.com/lcamichigan/cross-and-crescent#installing) the
cross-and-crescent package, and then enter in PowerShell or Terminal:

```sh
pdflatex -jobname logo '\documentclass{standalone}\usepackage{cross-and-crescent}\begin{document}\begin{tikzpicture}[scale=45bp/8cm]\crossAndCrescentSetMacros\draw[line width=0.5bp]\crossAndCrescentPath\end{tikzpicture}\end{document}'
```
