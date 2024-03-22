# Copacetic Extra Fonts [![License](https://img.shields.io/badge/License-SIL_OFLv1.1-green)](http://scripts.sil.org/OFL)

Newly packed font files combining open-source typefaces [Inter](https://github.com/rsms/inter) for western character sets (Latin, Greek, etc) and [Noto Sans CJK](https://github.com/notofonts/noto-cjk) for CJK characters.

### Changelog
**1.0.4**
- Changed folder structure to avoid '+' for Linux https://github.com/realcopacetic/resource.fonts.copacetic/issues/2
- Added support for Simplified Chinese https://github.com/realcopacetic/resource.fonts.copacetic/issues/3

**1.0.3**
- Fixed extension point for kodi.resource.font.

**1.0.2**
- Updated fanart.

**1.0.1**
- Fixes for Kodi Addon-Checker fail.

**1.0.0** 
- Initial release.

### Notes
**Fontlab steps**
1) Open Inter-X.ttf and Noto-Sans-SC-X.ttf. Window > Tiled
2) Hide unfiltered glyphs
3) Delete Bopomofo glyphs from Inter
4) Delete Latin, Cyrillic, Greek glyphs from Noto
5) Noto > Font info. Family dimensions. Units per EM > 2816 to match Inter. "Scale glyphs and metrics to the new UPM value" checked.
6) Inter > Font info - Name update
7) Copy all glyphs from Noto for the scrips you want to add, one at a time. This will avoid copying duplicates of things not in he scrips you're actually interested in.
8) Append glyphs into Inter
9) Copy a single glyph to clear clipboard and speed up program
10) Search and delete duplicates with a .1 suffix
11) Window > Workspaces > Kerning
12) Noto > Kerning Pairs. Select all, copy and paste pairs into Inter
13) Noto > Kerning Classes. Select all, copy and paste classes into Noto
14) Window > Panel > Features
15) Hamburger > Create [kern] feature
16) Play button. Don't add missing glyphs. (Update features)
17) Font info > Unicode Ranges add in new ranges (Detect)
18) Save font, export TTF
19) Open font and check there are no reds


### License
---
Inter, Noto Sans CJK and this Font Software are all licensed under the SIL Open Font License, Version 1.1.

This license is copied below, and is also available with a FAQ at:
http://scripts.sil.org/OFL

-----------------------------------------------------------
SIL OPEN FONT LICENSE Version 1.1 - 26 February 2007
-----------------------------------------------------------

PREAMBLE
The goals of the Open Font License (OFL) are to stimulate worldwide
development of collaborative font projects, to support the font creation
efforts of academic and linguistic communities, and to provide a free and
open framework in which fonts may be shared and improved in partnership
with others.

The OFL allows the licensed fonts to be used, studied, modified and
redistributed freely as long as they are not sold by themselves. The
fonts, including any derivative works, can be bundled, embedded,
redistributed and/or sold with any software provided that any reserved
names are not used by derivative works. The fonts and derivatives,
however, cannot be released under any other type of license. The
requirement for fonts to remain under this license does not apply
to any document created using the fonts or their derivatives.

DEFINITIONS
"Font Software" refers to the set of files released by the Copyright
Holder(s) under this license and clearly marked as such. This may
include source files, build scripts and documentation.

"Reserved Font Name" refers to any names specified as such after the
copyright statement(s).

"Original Version" refers to the collection of Font Software components as
distributed by the Copyright Holder(s).

"Modified Version" refers to any derivative made by adding to, deleting,
or substituting -- in part or in whole -- any of the components of the
Original Version, by changing formats or by porting the Font Software to a
new environment.

"Author" refers to any designer, engineer, programmer, technical
writer or other person who contributed to the Font Software.

PERMISSION AND CONDITIONS
Permission is hereby granted, free of charge, to any person obtaining
a copy of the Font Software, to use, study, copy, merge, embed, modify,
redistribute, and sell modified and unmodified copies of the Font
Software, subject to the following conditions:

1) Neither the Font Software nor any of its individual components,
in Original or Modified Versions, may be sold by itself.

2) Original or Modified Versions of the Font Software may be bundled,
redistributed and/or sold with any software, provided that each copy
contains the above copyright notice and this license. These can be
included either as stand-alone text files, human-readable headers or
in the appropriate machine-readable metadata fields within text or
binary files as long as those fields can be easily viewed by the user.

3) No Modified Version of the Font Software may use the Reserved Font
Name(s) unless explicit written permission is granted by the corresponding
Copyright Holder. This restriction only applies to the primary font name as
presented to the users.

4) The name(s) of the Copyright Holder(s) or the Author(s) of the Font
Software shall not be used to promote, endorse or advertise any
Modified Version, except to acknowledge the contribution(s) of the
Copyright Holder(s) and the Author(s) or with their explicit written
permission.

5) The Font Software, modified or unmodified, in part or in whole,
must be distributed entirely under this license, and must not be
distributed under any other license. The requirement for fonts to
remain under this license does not apply to any document created
using the Font Software.

TERMINATION
This license becomes null and void if any of the above conditions are
not met.

DISCLAIMER
THE FONT SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
OF COPYRIGHT, PATENT, TRADEMARK, OR OTHER RIGHT. IN NO EVENT SHALL THE
COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
INCLUDING ANY GENERAL, SPECIAL, INDIRECT, INCIDENTAL, OR CONSEQUENTIAL
DAMAGES, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF THE USE OR INABILITY TO USE THE FONT SOFTWARE OR FROM
OTHER DEALINGS IN THE FONT SOFTWARE.
