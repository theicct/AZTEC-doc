# AZTEC Documentation Update Guide

## Set-up

1. Clone the documentation repository
   - `git clone https://github.com/theicct/AZTEC-doc`
   - This is a _public_ repository – do not commit any code or sensitive information!
2. Make sure you have access to the latest version of the shared Word document

## Dependencies
1. [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)
2. [pandoc](https://pandoc.org/index.html) version 2.10.0 - install with `conda install -c conda-forge pandoc=2.10.0`
3. (Optional) Install a Markdown editor
4. (Optional) Install [Jekyll](https://jekyllrb.com/) if you intend to test the documentation changes locally


## Updating the documentation

1. Write your updates in the Word version
2. Get review, as necessary
3. Save as a .pdf file to the _versions_ folder with the name _AZTEC vX.Y Model Documentation.pdf_ where _X_ and _Y_ reference the model version, e.g. _AZTEC v1.6 Model Documentation.pdf_ (make sure you hide all markup before exporting)
4. If you added images to the Word document, add them to the _assets_ folder
5. Copy your changes to a Markdown version of the documentation either manually or automatically
   - 5a. Copy manually
     - Make a copy of the latest Markdown version of the documentation, using the same naming convention (for example, if the latest documentation is `v1.5.md`, create a copy named `v1.6.md`, matching the version of the AZTEC model)
     - Add your changes to the new Markdown file using your favorite Markdown editor
     - If you added images in step 4, add them to the file by inserting the following in the document: `![](/AZTEC-doc/assets/[filename])` where `[filename]` is the name of the image
     - Add the following to the top and bottom of your Markdown file, respectively: 
       ```
       ---
       layout: page
       title: 'AZTEC vX.Y Documentation'
       permalink: /versions/vX.Y/
       ---
       ```
       ```
       <button name='download' onclick="location.href='../AZTEC vX.Y Model Documentation.pdf'">Download as PDF</button>
       ```
   -  5b. Copy automatically
      - Edit the file path in _shared_version.sh_ to point to the Word version
      - If you added images in step 4, update the `IMG_MAP` in _doc_to_page.py_
      - Run the _copy_doc.sh_ bash script
6. (Optional) Test your changes locally
   - First, temporarily remove all references to the `AZTEC-doc/` directory (it becomes the baseurl once served by GitHub) from the Markdown documentation file and the _config.yml file
   - run `jekyll serve`
   - Make sure you add back in the references to `AZTEC-doc/`
7. Add and commit the new documentation files
   - `git add versions/vX.Y.md versions/AZTEC vX.Y Model Documentation.pdf`
   - `git commit -m "[Useful description of changes]"`
8. Push your changes, wait a minute, then check to make sure the [online version](https://theicct.github.io/AZTEC-doc) updated correctly
