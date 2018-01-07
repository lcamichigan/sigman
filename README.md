# Sigman

[![Build status](https://ci.appveyor.com/api/projects/status/91u8bs1bmmv0jwn4?svg=true)](https://ci.appveyor.com/project/lcamichigan/sigman)

This is a collection of resources for creating issues of _The Sigman_, the
newsletter of [Sigma Zeta of ΛΧΑ](http://lcamichigan.com).

## Contents

* [Getting Started](#getting-started)
  * [On Windows](#on-windows)
  * [On macOS](#on-macos)
* [Creating an InDesign File](#creating-an-indesign-file)
* [Guidelines for Writing Articles](#guidelines-for-writing-articles)
* [About _The Sigman_ Template](#about-the-sigman-template)

## Getting Started

To create an issue of _The Sigman_, you need the free
[Zip](http://www.info-zip.org/Zip.html) utility and
[Adobe InDesign](https://www.adobe.com/products/indesign.html); visit
https://www.adobe.com/creativecloud/plans.html for more information about
InDesign.

You also need the OpenType version of the font
[Linux Libertine](http://www.linuxlibertine.org), and additionally:

| Font                                                                     | Download URL                                                             |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------|
| [Arvo](https://fonts.google.com/specimen/Arvo)                           | https://github.com/google/fonts/raw/master/ofl/arvo/Arvo-Regular.ttf     |
| [Damion](https://fonts.google.com/specimen/Damion)                       | https://github.com/google/fonts/raw/master/ofl/damion/Damion-Regular.ttf |
| [League Spartan](https://www.theleagueofmoveabletype.com/league-spartan) | https://github.com/theleagueof/league-spartan/archive/master.zip         |

### On Windows

To install Zip:

1. Click ftp://ftp.info-zip.org/pub/infozip/win32/zip300xn-x64.zip and download
   zip300xn-x64.zip to your Downloads folder.

2. Right-click zip300xn-x64.zip in your Downloads folder, choose Extract All,
   and then click Extract to extract a folder named zip300xn-x64.

3. Right-click zip300xn-x64.zip in the zip300xn-x64 folder you just extracted,
   choose Extract All, and then click Extract to extract another folder named
   zip300xn-x64.

4. Move this second zip300xn-x64 folder to C:\Program Files.

### On macOS

Zip is included with macOS.

## Creating an InDesign File

First, download this repository as a ZIP archive. To do this, click
[here](https://github.com/lcamichigan/sigman/archive/master.zip). Unzip the
archive wherever you wish. To create a Sigman.idml InDesign file from the files
in this repository, enter in PowerShell:

```powershell
cd 'Sigman IDML'
Start-Process "$env:ProgramFiles\zip300xn-x64\zip" -ArgumentList '-X0', '..\Sigman.idml', 'mimetype' -Wait
Start-Process "$env:ProgramFiles\zip300xn-x64\zip" -ArgumentList '--recurse-paths', '--no-dir-entries', '-X9', '..\Sigman.idml', '*', '--exclude', 'mimetype' -Wait
```

or in Command Prompt:

```batch
cd "Sigman IDML"
"%ProgramFiles%\zip300xn-x64\zip" -X0 ..\Sigman.idml mimetype
"%ProgramFiles%\zip300xn-x64\zip" --recurse-paths --no-dir-entries -X9 ..\Sigman.idml * --exclude mimetype
```

or in Terminal:

```sh
cd 'Sigman IDML'
zip -X0 ../Sigman.idml mimetype
zip --recurse-paths --no-dir-entries -X9 ../Sigman.idml * --exclude *.DS_Store mimetype
```

## Guidelines for Writing Articles

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

* Use a right single quotation mark (’), not a straight single quote (') or a
  left single quotation mark (‘), to abbreviate a year.

  _Correct:_ George Spasyk&nbsp;’49

  _Incorrect:_ George Spasyk&nbsp;‘49

  Note that Microsoft Word’s “smart quotes” feature often uses the wrong
  quotation mark in this case.

* Use _italics_ for emphasis, not bold or underlining.

* If you’re not writing a High Alpha or High Pi letter, avoid writing in the
  first person. If you need to refer to yourself in an article, use _this
  writer_ or _this author_ instead of _me_ or _I_. Use _Sigma_, _the
  undergraduates_, or _the active chapter_ instead of _we_ or _us_.

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
  titles, for example, “The meeting was chaired by Brother George
  Spasyk&nbsp;’49. George is a brother from Sigma.”

* Don’t use _rushees_ to refer to _prospective members_.

* Don’t describe something as _historic_ or _momentous_ unless it is. Sigma’s
  100th anniversary was historic. Having a formal dance go off without a hitch
  is excellent, but not historic.

* Don’t capitalize seasons like _fall_ and _winter_.

* Don’t use _the house_ to refer to _the chapter house_.

* Use _Sigma_ instead of _Sigma Zeta_ and _Sigma Zeta of ΛΧΑ_.

* Use _U&#x2011;M_ or _Michigan_ when _University of Michigan_ is too verbose.
  Don’t use _U of M_.

* Follow _Interfraternity Council_ with its initialism in parentheses (IFC) on
  first use, and then use the initialism only. Unless you’re writing about more
  than one Interfraternity Council, there’s no need to precede _IFC_ with
  _Michigan_ or _U&#x2011;M_. Don’t hyphenate _Interfraternity_.

## About _The Sigman_ Template

_The Sigman_ template is based on issues of _The Sigman_ from 1939–46 (available
at http://lcamichigan.com/alumni-news#sigman). The
[nameplate](https://en.wikipedia.org/wiki/Nameplate_(publishing)) of these
issues appears to be set in a form of
[Caslon](https://en.wikipedia.org/wiki/Caslon) that’s similar to
[Big Caslon](https://store.typenetwork.com/foundry/cartercone/fonts/big-caslon/regular).
Body text appears to be a form of
[Century](https://en.wikipedia.org/wiki/Century_type_family). Headlines use a
variety of typefaces: [Bodoni](https://en.wikipedia.org/wiki/Bodoni),
[Caslon](https://en.wikipedia.org/wiki/Caslon),
[Kaufmann](https://en.wikipedia.org/wiki/Kaufmann_(typeface))
[Memphis](https://en.wikipedia.org/wiki/Memphis_(typeface)), and either
[Metro No. 2](https://en.wikipedia.org/wiki/Metro_(typeface)) or
[Spartan](https://en.wikipedia.org/wiki/Spartan_(typeface)).

The nameplate in the template uses Big Caslon Medium (the version included with
macOS High Sierra 10.13) at 48&nbsp;pt with tracking at 200 thousandths of an
em.

Here are the free fonts used in place of commercially available originals:

| Font name  | Free alternative                                                         |
|------------|--------------------------------------------------------------------------|
| Kaufmann   | [Damion](https://fonts.google.com/specimen/Damion)                       |
| Memphis    | [Arvo](https://fonts.google.com/specimen/Arvo)                           |
| Spartan    | [League Spartan](https://www.theleagueofmoveabletype.com/league-spartan) |
