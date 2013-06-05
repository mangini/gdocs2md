gdocs2md
========

A simple Google Apps script to convert a properly formatted Google Drive Document to the markdown (.md) format. 

## Usage
  * Open your Google Drive document (http://drive.google.com)
  * Tools -> Script Editor. Ignore (close) if you see a popup, clear the myFunction() default empty function and paste the [converttomarkdown.gapps](https://raw.github.com/mangini/gdocs2md/master/converttomarkdown.gapps) contents into the code editor
  * File -> Save
  * Run -> ConvertToMarkdown (First run will require you to authorize it. Authorize and run again)

The converted Markdown will be immediately sent as an attachment to your email. Images will be attached as well.

You can run the script again in the same document whenever you want, just clicking in Tools -> Script Manager -> Run. Every run will send a new email.


## Interpreted formats
  * *NEW*: images are correctly extracted and sent as attachments
  * *NEW*: Table of contents is replaced by `[[TOC]]`
  * paragraphs are separated by two newlines
  * text styled as heading 1, 2, 3, etc is converted to Markdown heading: #, ##, ###, etc
  * text formatted with Courier New is backquoted: ``text``
  * links are converted to MD format: `[anchortext](url)`
  * bullet lists are converted to "`*`" MD format appropriately, including nested lists
  * blocks of text delimited by "--- class whateverclassnameyouwant" and "---" are converted to `<div class="whateverclassnameyouwant"></div>` 
  * blocks of text delimited by "--- source code" and "---" are converted to `<pre></pre>` and prefixed by 4 empty spaces
  * "--- jsperf `<testID>`" is replaced by an iframe that shows an interactive chart of a JSPerf test. The `<testID>` is the last part of the URL of the Browserscope anchor in your JSPerf test. Something like `"agt1YS1wcm9maWxlcnINCxIEVGVzdBjlm_EQDA"` in the URL `http://www.browserscope.org/user/tests/table/agt1YS1wcm9maWxlcnINCxIEVGVzdBjlm_EQDA`
 
