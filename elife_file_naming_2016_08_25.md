# eLife file naming and asset IDs 

## File naming pattern (excluding parent zip file)

    elife-<f-id>(-<asset><a-id>)(-<sub-asset><sa-id>)(-<data><d-id>)(-<code><c-id>)(-<video><m-id>)(-<reporting standard><repstand-id>)(-<transparent reporting form><transrepform-id>)(-<supplementary file><supp-id>)|(-r<revision>).<ext>

Brackets represent optional components. Pipe represents a choice on component, depending on state in the publishing system.

Every file type must have the file type suffix (e.g. .tiff), for example:

    elife-00666-fig1.tiff

### Components

#### `<f-id>`

This is the file id and is the numerical digit that is used to make up part of the DOI for an article (`<article-id pub-id-type="doi">`). For example an eLife article with the following DOI `/10.7554/eLife.00666` will have an f-id of `00666`.

#### `<asset>`

This refers to an asset file related to an article:
- a figure (fig)
- a figure supplement (figsupp)
- a source code file (code)
- a source data file (data)
- a video (video)
- a supplementary file (supp)
- the figures pdf (figures) 
- a reporting standard (repstand)
- inline graphics (inf)
- a transparent reporting form (transrepform)

Decision letter and author response are at the level of assets but are not seperate files and do not require a number suffix in the name and are not seperate files.
- decision letter (dec)
- author response (resp)

Appendices, tables and boxes are at the level of assets but are not seperate files.
- appendix (app)
- table (table)
- Box (box)

All assets could have any sub assets and some sub assets can have further assets (see examples below).

#### `<a-id>`

The `a-id` is the asset id, and indicates the order of an asset in the article. For example an
article with three figures will have the following asset files:

- elife-00666-fig1.tiff
- elife-00666-fig2.tiff
- elife-00666-fig3.tiff

#### `<sub-asset>`

The following asset is actually a sub-asset:
- a figure supplement (figsupp)

The following assets could be assets at the parent or child level:

- source code (code)
- source data (data)
- video (video)

#### `<sa-id>`

The `sa-id` is the asset id. Some assets will have sub-assets, eg figure supplements (figsupp), source data (data), or source code (code). These are indicated by the sub-asset component. For example:

- elife-00666-fig1-figsupp1.tiff
- elife-00666-fig1-code1.xml
- elife-00666-app1-fig1.tiff
- elife-00666-fig3-video1.mp4

Some sub-assets have further sub-asset ids, For example:

- elife-00666-fig1-figsupp1-code1.xml
- elife-00666-app1-fig1-figsupp1-code1.xml
- elife-00666-fig3-figsupp1-data1.xls

#### `<data>`

Sometimes there is source data at a parent level, but sometimes assets will have source data files associated with them. These data files are indicated by the presence of a `data` in the filename. For example source data at the top level will be called:

    elife-00666-data1.xlsx

For example source data to figure 2 will be called:

    elife-00666-fig2-data1.rtf

For example source data to figure 3-figure supplement 1 will be called:

    elife-00666-fig3-figsupp1-data1.xls

#### `<code>`

Sometimes there is source code at a parent level, but sometimes assets will have source code files associated with them. These source code files are indicated by the presence of a `code` in the filename.

For example source code at the top level will be called:

    elife-00666-code1.xml

For example source code to figure 2 will be called:

    elife-00666-fig2-code1.rtf

For example source code to figure 3-figure supplement a will be called:

    elife-00666-fig3-figsupp1-code1.r

#### inline graphics

Inline graphics are used to represent symbols that cannot come from the font palet but are required to represent something, for example in a figure.
These are named sequentially throughout a file (irrespective of where they will be found) and will never have sub assets.

#### Author response 

All assets in this part of the article require the asset of "resp", followed by the asset or sub asset. For example, a Author response image 1 will be named:

    elife-00666-resp-fig-1.tiff

Or a Author response video 1 as:

    elife-00666-resp-video1.mp4

#### Appendices

All assets in an appendix require the asset of "appX" (where X is the appendix number - even if there is only one appendix it is numbered), followed by the asset or sub asset. For example, a Appendix figure 1 will be named:

    elife-00666-app1-fig-1.tiff

An Appendix figure 1 figure supplement 1 will be named:

    elife-00666-app1-fig-1-figsupp1.tiff

Or an  Appendix video 1 as:

    elife-00666-app1-video1.mp4

#### Tables 

Tables do not contain figures unless they are inline graphics. However, they can contain source data, for example, so this would be named:

    elife-00666-table1-data1.tiff

#### Boxes 

All assets in a box require the asset of "boxX" (where X is the box number - even if there is only one box it is numbered), followed by the asset or sub asset. For example, a Box figure 1 will be named:

    elife-00666-box1-fig-1.tiff

A Box figure 1 figure supplement 1 will be named:

    elife-00666-box1-fig-1-figsupp1.tiff

Or a Box video 1 as:

    elife-00666-box1-video1.mp4

## Zip file naming pattern

### Components

#### `<status>`

This is either `poa` (publish on accept) or `vor` (version of record).
The content processor only produced vor content.

#### r`<revision>`

When supplying content at each stage, the zip file package is delivered to the eLife AWS and requires a -rX suffix (where the X is a sequential number depending on the number of times it is required to be resupplied)

At each stage of the production process an output of the content is delivered to the subfolders of this AWS bucket: elife-production-processes

- elife-production-preedited - after pre-editing is complete the output is delivered here
- elife-production-initial-qc - after eLife has checked the pre-editing the complete the output is delivered here
- elife-production-copyedited - after copyediting the complete the output is delivered here
- Features ONLY: elife-production-featurechecked - after features have signed off on an article the complete the output is delivered here
- elife-production-authorcorrected  - after author has signed off on an article the complete the output is delivered here
- elife-production-productionchecked - after production has signed off on an article post-author the complete the output is delivered here


??????? elife-production-revised 

When content is delivered to the continuum website it is delivered to this AWS bucket: elife-production-final

Example file name:
elife-00666-vor-r1


## XML Identifiers and xref links

### Components

#### Figures

    x-ref ref-type="fig"
    id="fig1"

#### Figure supplements

    x-ref ref-type="fig"
    id="fig1s1"

#### Figures within author response

    x-ref ref-type="fig"
    id="resp-fig1"

#### Figure supplements within author response

    x-ref ref-type="fig"
    id="resp-fig1s1"

#### Figures within appendices

    x-ref ref-type="fig"
    id="app1-fig1"

#### Figure supplements within appendices

    x-ref ref-type="fig"
    id="app1-fig1s1"

#### Chemical structures

    x-ref ref-type="fig"
    id="chem1"

#### Schemes

    x-ref ref-type="fig"
    id="scheme1"

#### Source data as primary asset

    xref ref-type="supplementary-material"
    id="sourcedata1"

#### Source data as sub asset

    xref ref-type="supplementary-material"
    id="sdata1"

#### Source code as primary asset

    xref ref-type="supplementary-material"
    id="scode1"

#### Source code as sub asset

    xref ref-type="supplementary-material"
    id=""

#### Videos as primary asset

    xref ref-type="other"
    id="video1"

#### Videos as sub asset

    xref ref-type="other"
    id="fig1-video1"

#### Tables

    xref ref-type="table"
    id="table1"

#### Inline tables

    xref ref-type="inlinetable1"
    id="inlinetable"

#### Boxes

    xref ref-type="box"
    id="box1"

#### Appendices

Appendices are a section within an article, so their id is a reflection on their order in the sections of an article, eg id="s8" (indicates this appendix is the 8th <sec> of this article). However, the sec does have a sec-type of "appendix1"

    xref ref-type="fig"
    id="app1-fig1'

    xref ref-type="table"
    id=""app1-table1""

#### Reporting standards

    xref ref-type="supplementary-material"
    id="repstand1"

#### Transparent reporting form
    xref ref-type="transrepform"
    id="transrepform"

#### Decision letter

Decision letters are a sub-article of the main article, the article-type attribuite is "decision-letter" and their ID is "SA1"

#### Author response

Author responses are a sub-article of the main article, the article-type attribuite is "reply" and their ID is "SA2"

    xref ref-type="fig"
    id="resp-fig1'

    xref ref-type="table"
    id="resp-table1"

#### Equations

Equations are not assets, but they do have ids that have a style.

    xref ref-type="equation"
    - id="equ1""

#### Other Xref link ids

- `aff1` aff followed by seqential number. Designates the affiliation address
- `equal-contrib1` equal-contrib followed by seqential number. Designates any equal contributions, if there is more than 1 set of equal contributions then the second set take the number 2 etc
- `pa1` if there is a present address for an author it takes this id
- `fn1` if there are any other footnotes for authors, they take this id. This can be used for deceased but also for random other comments
- `fund1` link to funding
- `conf1` link to conflict (cometing interests) statement
- `con1` link to authors contribution
- `dataset1` link to a datasert listed in the dataset section, which the author was author of
- `bib1` link to reference in reference list

#### Section IDs

Every level 1 section has a sec-type attribute and and id s1 etc

Sub sections cary IDs only and follow a numerical ordering, using is dashnumber suffix, eg section 1 has a lavel 2 section: s1-1
section 2, level 3 heading number 1: s2-1-1

## DOIs

All "assets" have sub-DOIs, with the exception of equations.

## Additional information

- All assets shuld be cited in the mean text and crosslinked via an xref.
- If a source code file or source data file is not attached to a specific figure, it is placed in the <sec sec-type="supplementary-material">.
However, if it is attached to a specific figure it is listed as part of the figure tagging and not repeated in this section.

