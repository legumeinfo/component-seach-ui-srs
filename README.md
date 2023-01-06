## Table of contents
 - [Overview](#overview)<br>
 - [Gene search query](#gene-search)<br>
 - [Intermediate report](#intermediate-report)<br>
 - [target URLs](#target-urls)<br>

### Overview  <a name="overview"/>

This document provides specification for interactive search and reporting UI components. Most (potentially all) of the content in this repository should be in this README document. However, we'll test whether READMEs in subdirectories are rendered as HTML; this would be a convenient way to make the specification more modular.

#### Problem statement
This section will describe the main problem/task to be accomplished. Essentially: given queries of a specified type, return results appropriate to the use case, structured appropriately.

#### Proposed solution
XX description

### Key Features
This will be the core of the project SRS. It should explicit, understandable by the client but easy to interprate to code by developers. To achieve this write it in user story format; The title is the story and the bullets are the "checklist"  
##### User Auth
- Each user using the system has a login credential to access system functionalities.
- User should be able to login in with email and a password
- Password should be more than 8 characters
- Etc
##### Roles and Permissions
- The system has permissions and roles for users. 
- Users are assigned different role and permission to perform different action in the system - for example approvals and the roles also give access to different sections in the system
- Etc
##### Travel allowance and expense 
- Travel expense tracker attract the allowance awarded to employee traveling and their travel expense.
- Etc

### Gene search query <a name="gene-search"/>
Enter a gene name
```
  Accepts bare or prefixed IDs, e.g. 
    Phvul.004G049100 or phavu.G19833.gnm1.ann1.Phvul.004G049100 or 004G049100
    Glyma.19G041200 or glyma.Wm82.gnm4.ann1.Glyma.19G041200 or 19G041200
  Optional: specify organism. Drop-down list of genera and species? Or text-entry with auto-complete?
    Glycine, Glycine cyrtoloba, Glycine D3-tomentella, Glycine dolichocarpa, Glycine falcata, Glycine max, Glycine soja, Glycine stenophita, Glycine syndetika
```

### Intermediate report <a name="intermediate-report"/>
Within Jekyll-LIS or Jekyll-SoyBase:
```
  A table of matching genes (from all accessions matching the query string) and available resources.
  The links go to the respective tools.
  The GCV and Mine intermediate report pages are a good model of the listing of matching genes
    https://gcv.legumeinfo.org/gcv2/search?q=19G041200&sources=lis
    
  The Jekyll-Soybase report table might look like this, given a search on "19G041200" and no organism specified:
  
  Your search found these items and available tools:

    glyso.PI483463.gnm1.ann1.GlysoPI483463.19G041200
      Genome Context Viewer
      GlycineMine gene report
      Gene tree viewer
      Genome browser
      SoyBase classic gene report
      Pan-gene report (TBD)

    glyma.Wm82.gnm4.ann1.Glyma.19G041200
      Genome Context Viewer
      GlycineMine gene report
      Gene tree viewer
      Genome browser
      SoyBase classic gene report
      Pan-gene report

    glyma.Wm82.gnm2.ann1.Glyma.19G041200
      Genome Context Viewer
      GlycineMine gene report
      Gene tree viewer
      Genome browser
      SoyBase classic gene report
      Pan-gene report
```

### Example target URLs: <a name="target-urls"/>
```
  Genome Context Viewer
    https://gcv.soybase.org/gene;soybase=glyma.Wm82.gnm4.ann1.Glyma.19G041200
  GlycineMine gene page
    https://mines.legumeinfo.org/glycinemine/report.do?id=88499065
  Tree viewer for tree containing the gene
    https://funnotate.legumeinfo.org/?family=L_NHQNXR
  Phytozome gene page
    # Note: The syntenic ortholog of glyma.Wm82.gnm4.ann1.Glyma.19G041200 is GmISU01.19G034700
    https://phytozome-next.jgi.doe.gov/report/gene/Gmax_Wm82_a4_v1/Glyma.19G041200
  Phytozome browser
    https://phytozome-next.jgi.doe.gov/jbrowse/index.html?data=genomes%2FGmax_Wm82_a4_v1&loc=Gm19%3A5993195..5996633&tracks=Transcripts%2CAlt_Transcripts%2CPASA_assembly%2CBlastx_protein%2CBlatx_Fabidae&highlight=
  SoyBase classic gene page
    https://www.soybase.org/sbt/search/search_results.php?category=FeatureName&version=Wm82.a4.v1&search_term=Glyma.19G041200
```
