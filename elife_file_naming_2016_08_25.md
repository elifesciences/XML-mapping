# eLife file naming and IDs 

## File naming pattern (excluding parent zip file)

>
	`elife-<f-id>(-<asset><a-id>)(-<sub-asset><sa-id>)(-<data><d-id>)(-<code><c-id>)(-<video><m-id>)(-<reporting standard><repstand-id>)(-<supplementary file><supp-id>)|(-r<revision>).<ext>`

Brackets represent optional components. Pipe represents a choice on component, depending on state in the publishing system.


### Components

###### `<f-id>`

This is the file id and is the numerical digit that is used to make up part of the DOI for an article (`<article-id pub-id-type="doi">`). For example an eLife article with the following DOI `/10.7554/eLife.06659` will have an f-id of `06659`.


###### `<asset>`

This refers to an asset file related to an article:
- a figure (fig)
- source code (code)
- source data (data)
- video (videos)
- supplementary file (supp)
- the figures pdf (figures) 
- reporting standards (repstand)
- appendix(app)

Each of these assets require a suffixed number starting from 1 and going up sequentially, e.g. 
elife-06659-fig1

- decision letter (dec)
- author response (resp)

Decision letter and author response are at the level of assets but do not require a number.


All assets could have any sub assets.


###### `<a-id>`

The `a-id` is the asset id, and indicates the order of an asset in the article. For example an
article with three figures will have the following asset files:

- elife-00012-fig1.tiff
- elife-00012-fig2.tiff
- elife-00012-fig3.tiff

###### `<sub-asset>`

Some assets will have sub-assets, eg figure supplements (figsupp), source data (data), or source code (code). These are indicated by the sub-asset component.

###### `<sa-id>`

Some assets have sub-asset ids, for example, an article with three main figures, where one
figure has three figure supplements, and one figure has two figure supplements will have the following:

- elife-00012-fig1.tiff
- elife-00012-fig1-figsupp1.tiff
- elife-00012-fig1-figsupp2.tiff
- elife-00012-fig1-figsupp3.tiff
- elife-00012-fig2.tiff
- elife-00012-fig3.tiff
- elife-00012-fig3-figsupp1.tiff
- elife-00012-fig3-figsupp2.tiff

###### data

Sometimes there is source data at a parent level, but sometimes assets will have source data files associated with them. These data files are indicated by the presence of a `data` in the filename.

###### `<d-id>`

Assets can have multiple source data files associated with them, and these are distinguished with the
data id.

For example, an article with three main figures, where one figure has three figure supplements, and one figure has two figure supplements, and all have associated data, with some of them having multiple data files, could have the following:

- elife-00012-fig1.tiff
- elife-00012-fig1-data1.csv
- elife-00012-fig1-data2.csv
- elife-00012-fig1-figsupp1.tiff
- elife-00012-fig1-figsupp1-data1.csv
- elife-00012-fig1-figsupp2.tiff
- elife-00012-fig1-figsupp2-data1.csv
- elife-00012-fig1-figsupp3.tiff
- elife-00012-fig1-figsupp3-data1.mol
- elife-00012-fig2.tiff
- elife-00012-fig2-data1.txt
- elife-00012-fig3.tiff
- elife-00012-fig3-data.csv
- elife-00012-fig3-figsupp1.tiff
- elife-00012-fig3-figsupp1-data1.csv
- elife-00012-fig3-figsupp1-data2.csv
- elife-00012-fig3-figsupp1-data3.csv
- elife-00012-fig3-figsupp2.tiff
- elife-00012-fig3-figsupp2-data1.csv
- elife-00012-fig3-figsupp3.tiff
- elife-00012-fig3-figsupp3-data1.csv


###### code

Sometimes there is source code at a parent level, but sometimes assets will have source code files associated with them. These source code files are indicated by the presence of a `code` in the filename.

###### `<c-id>`

Assets can have multiple source code files associated with them, and these are distinguished with the
code id.

For example, an article with a top level source code, two main figures, where one figure has source code, and one figure has one figure supplement with source code:

- elife-00012-fig1.tiff
- elife-00012-fig1-code1.csv
- elife-00012-fig2.tiff
- elife-00012-fig2-figsupp1.tiff
- elife-00012-fig2-figsupp1-code1.csv
- elife-00012-code1.csv

##Complete list of sub components:

- figure -> fig
- figuresupplement -> figsupp
- supplementary file -> supp
- video -> video
- inline-media -> inf
- source code -> code
- source data -> data
- figures (PDF if the figures) -> figures
- reporting standards -> repstand [note: not inu se as at October, 2015]
- decision letter file, for example figure -> dec-fig
- appendix asset file, for example figure (each appendix gets a unique number X) -> appX-fig
- author response asset file, for example figure -> resp-fig

## Zip file naming pattern

###### `<status>`

This is either `poa` (publish on accept) or `vor` (version of record).

##### r`<revision>`

#####Example
- elife-00012-vor-r4.zip contains
- elife-00012.xml
- elife-00012.pdf
- elife-00012-figures.pdf
- elife-00012-fig1.tiff
- elife-00012-fig1-data1.csv
- elife-00012-fig1-data2.csv
- elife-00012-fig1-figsupp1.tiff
- elife-00012-fig1-figsupp1-data1.csv
- elife-00012-fig1-figsupp2.tiff
- elife-00012-fig1-figsupp2-data1.csv
- elife-00012-fig1-figsupp3.tiff
- elife-00012-fig1-figsupp3-data1.mol
- elife-00012-fig2.tiff
- elife-00012-fig2-data1.txt
- elife-00012-fig3.tiff
- elife-00012-fig3-data.csv
- elife-00012-fig3-figsupp1.tiff
- elife-00012-fig3-figsupp1-data1.csv
- elife-00012-fig3-figsupp1-data2.csv
- elife-00012-fig3-figsupp1-data3.csv
- elife-00012-fig3-figsupp2.tiff
- elife-00012-fig3-figsupp2-data1.csv
- elife-00012-fig3-figsupp3.tiff
- elife-00012-fig3-figsupp3-data1.csv

## XML Identifiers

#####Figures
X-ref ref-type+"fig"
id="fig1"

#####Figure supplements
id="fig1s1"

#####Source data
ref-type="supplementary-material"
id="SD1-data"

#####Source code
xref ref-type="supplementary-material"
id="SD1-data"

#####Videos
xref ref-type="other"
id="video1"

#####Tables
xref ref-type="table"
id="tbl"

#####Boxes
xref ref-type="other"
id="box1"

#####Appendices
Appendices are a section within an article, so their id is a reflection on tehir order in the sections of an article, eg id="s8" (indicates this appendix is the 8th <sec> of this article). However, the sec does have a sec-type of "appendix"

figure ID: app1-fig1
xref ref-type="fig"

Table ID: app1-tbl1
xref ref-type="table"


#####Reporting standards

#####Major datasets


#####Equations

Equations are not assets, but they do have ids that have a style.

## DOIs
All "assets" have sub-DOIs, with the exception of equations.



## Additional information
If a source code file or source data file is not attached to a specific figure, it is placed in the <sec sec-type="supplementary-material">.
However, if it is attached to a specific figure it is listed as part of the figure tagging and not repeated in this section.

