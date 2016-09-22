# eLife file naming and asset IDs 

## File naming pattern (excluding parent zip file)

>
	`elife-<f-id>(-<asset><a-id>)(-<sub-asset><sa-id>)(-<data><d-id>)(-<code><c-id>)(-<video><m-id>)(-<reporting standard><repstand-id>)(-<supplementary file><supp-id>)|(-r<revision>).<ext>`

Brackets represent optional components. Pipe represents a choice on component, depending on state in the publishing system.

Every file type must have the file type suffix (e.g. .tiff), for example:

elife-00666-fig1.tiff


### Components

###### `<f-id>`

This is the file id and is the numerical digit that is used to make up part of the DOI for an article (`<article-id pub-id-type="doi">`). For example an eLife article with the following DOI `/10.7554/eLife.00666` will have an f-id of `00666`.


###### `<asset>`

This refers to an asset file related to an article:
- a figure (fig)
- a figure supplement (figsupp)
- source code (code)
- source data (data)
- video (video)
- supplementary file (supp)
- the figures pdf (figures) 
- reporting standards (repstand)
- inline graphics (inf)


Decision letter and author response are at the level of assets but are not seperate files and do not require a number suffix in the name and are not seperate files.
- decision letter (dec)
- author response (resp)

Appendices, tables and boxes are at the level of assets but are not seperate files.
- appendix (app)
- table (table)
- Box (box)

All assets could have any sub assets and some sub assets can have further assets (see examples below).


###### `<a-id>`

The `a-id` is the asset id, and indicates the order of an asset in the article. For example an
article with three figures will have the following asset files:

- elife-00666-fig1.tiff
- elife-00666-fig2.tiff
- elife-00666-fig3.tiff

###### `<sub-asset>`

Some assets will have sub-assets, eg figure supplements (figsupp), source data (data), or source code (code). These are indicated by the sub-asset component. For example:

- elife-00666-fig1-figsupp1.tiff

###### `<sa-id>`

Some assets have sub-asset ids, for example, an article with three main figures, where one
figure has three figure supplements, and one figure has two figure supplements will have the following:

- elife-00666-fig1.tiff
- elife-00666-fig1-figsupp1.tiff
- elife-00666-fig1-figsupp2.tiff
- elife-00666-fig1-figsupp3.tiff
- elife-00666-fig2.tiff
- elife-00666-fig3.tiff
- elife-00666-fig3-figsupp1.tiff
- elife-00666-fig3-figsupp2.tiff

###### data

Sometimes there is source data at a parent level, but sometimes assets will have source data files associated with them. These data files are indicated by the presence of a `data` in the filename. For example source data at the top level will be called:

elife-00666-data1.xlsx

For example source data to figure 2 will be called:

elife-00666-fig2-data1-v1.rtf

For example source data to figure 2-Figure Supplement 3 will be called:

elife-00666-fig3-figsupp1-data1.rtf

###### code

Sometimes there is source code at a parent level, but sometimes assets will have source code files associated with them. These source code files are indicated by the presence of a `code` in the filename.

For example source code at the top level will be called:

elife-00666-code1.xlsx

For example source code to figure 2 will be called:

elife-00666-fig2-code1-v1.rtf

For example source code to figure 2-Figure Supplement 3 will be called:

elife-00666-fig3-figsupp1-code1.rtf


###### inline graphics
Inline graphics are used to represent symbols that cannot come from the font palet but are required to represent something, for example in a figure.
These are named sequentially throughout a file (irrespective of where they will be found) and will never have sub assets.

###### Author response 
All assets in this part of the article require the asset of "resp", followed by the asset or sub asset. For example, a Author response image 1 will be named:

elife-00666-resp-fig-1.tiff

Or a Author response video 1 as:

elife-00666-resp-media1.mp4


###### Appendices
All assets in an appendix require the asset of "appX" (where X is the appendix number - even if there is only one appendix it is numbered), followed by the asset or sub asset. For example, a Appendix figure 1 will be named:

elife-00666-app1-fig-1.tiff

a Appendix figure 1 figure supplement 1 will be named:

elife-00666-app1-fig-1-figsupp1.tiff

Or a  Appendix video 1 as:

elife-00666-app1-media1.mp4


###### Tables 
Tables do not contain figures unless they are inline graphics. However, they can contain source data for example, so would be named:

elife-00666-table1-data1.tiff

###### Boxes 
All assets in a box require the asset of "boxX" (where X is the box number - even if there is only one box it is numbered), followed by the asset or sub asset. For example, a Box figure 1 will be named:

elife-00666-box1-fig-1.tiff

a Box figure 1 figure supplement 1 will be named:

elife-00666-box1-fig-1-figsupp1.tiff

Or a Box video 1 as:

elife-00666-box1-media1.mp4

## Zip file naming pattern

###### `<status>`

This is either `poa` (publish on accept) or `vor` (version of record).

##### r`<revision>`

#####Example
- elife-00666-vor-r4.zip contains
- elife-00666.xml
- elife-00666.pdf
- elife-00666-figures.pdf
- elife-00666-fig1.tiff
- elife-00666-fig1-data1.csv
- elife-00666-fig1-data2.csv
- elife-00666-fig1-figsupp1.tiff
- elife-00666-fig1-figsupp1-data1.csv
- elife-00666-fig1-figsupp2.tiff
- elife-00666-fig1-figsupp2-data1.csv
- elife-00666-fig1-figsupp3.tiff
- elife-00666-fig1-figsupp3-data1.mol
- elife-00666-fig2.tiff
- elife-00666-fig2-data1.txt
- elife-00666-fig3.tiff
- elife-00666-fig3-data.csv
- elife-00666-fig3-figsupp1.tiff
- elife-00666-fig3-figsupp1-data1.csv
- elife-00666-fig3-figsupp1-data2.csv
- elife-00666-fig3-figsupp1-data3.csv
- elife-00666-fig3-figsupp2.tiff
- elife-00666-fig3-figsupp2-data1.csv
- elife-00666-fig3-figsupp3.tiff
- elife-00666-fig3-figsupp3-data1.csv

## XML Identifiers and xref links

#####Figures
x-ref ref-type="fig"
id="fig1"

#####Figure supplements
x-ref ref-type="fig"
id="fig1s1"

#####Source data
xref ref-type="supplementary-material"
id="sd1"

#####Source code
xref ref-type="supplementary-material"
id="sd1"

#####Videos
xref ref-type="other"
id="video1"

#####Tables
xref ref-type="table"
id="table"

#####Inline tables
xref ref-type="inlinetable"
id="inlinetable"

#####Boxes
xref ref-type="box"
id="box1"

#####Appendices
Appendices are a section within an article, so their id is a reflection on their order in the sections of an article, eg id="s8" (indicates this appendix is the 8th <sec> of this article). However, the sec does have a sec-type of "appendix"

figure ID: app1-fig1
xref ref-type="fig"

Table ID: app1-table1
xref ref-type="table"


#####Reporting standards
xref ref-type="supplementary-material"
id="sd1"

#####Author response


#####Equations
Equations are not assets, but they do have ids that have a style.

#####Other Xref link ids
aff1 - aff followed by seqential number. Designates the affiliation address
equal-contrib1 - equal-contrib followed by seqential number. Designates any equal contributions, if there is more than 1 set of equal contributions then the second set take the number 2 etc

pa1 - if there is a present address for an author it takes this id
fn1 - if there are any other footnotes for authors, they take this id. This can be used for deceased but also for random other comments
fund1 - link to funding
conf1 - link to conflict (cometing interests) statement
con1 - link to authors contribution
dataset1 - link to a datasert listed in the dataset section, which the author was author of
bib1 - link to reference in reference list

#####Section IDs
Every level 1 section has a sec-type attribute and and id s1 etc

Sub sections cary IDs only and follow a numerical ordering, using is dashnumber suffix, eg section 1 has a lavel 2 section: s1-1
section 2, level 3 heading number 1: s2-1-1

## DOIs
All "assets" have sub-DOIs, with the exception of equations.
Equation ID: equ1
xref ref-type="equation"



## Additional information
- All assets shuld be cited in the mean text and crosslinked via an xref.
- If a source code file or source data file is not attached to a specific figure, it is placed in the <sec sec-type="supplementary-material">.
However, if it is attached to a specific figure it is listed as part of the figure tagging and not repeated in this section.

