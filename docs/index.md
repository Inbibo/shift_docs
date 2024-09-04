# Introduction

## Static

<figure style="width:80%; margin-left:10%" markdown>
      ![UI](images/ui.png)
      <figcaption><b>Figure 1</b>: Markdown figure with width and margin.</figcaption>
</figure>

<figure markdown>
      ![UI](images/ui.png)
      <figcaption><b>Figure 2</b>: Markdown figure with no style. </figcaption>
</figure>

<center>
      <figure markdown>
            ![UI](images/ui.png)
            <figcaption><b>Figure 3</b>: Markdown figure centered with no style. </figcaption>
      </figure>
</center>

<figure>
      <img src="images/ui.png" alt="UI">
      <figcaption><b>Figure 4</b>: Figure with image</figcaption>
</figure>


<img src="images/ui.png" alt="UI">
<b>Figure 5</b>: Plain Image

## Gifs

<figure style="width:80%; margin-left:10%" markdown>
      ![UI](images/giftest.gif)
      <figcaption><b>Figure 1</b>: Markdown figure with width and margin.</figcaption>
</figure>

<figure markdown>
      ![UI](images/giftest.gif)
      <figcaption><b>Figure 2</b>: Markdown figure with no style. </figcaption>
</figure>

<center>
      <figure markdown>
            ![UI](images/giftest.gif)
            <figcaption><b>Figure 3</b>: Markdown figure centered with no style. </figcaption>
      </figure>
</center>

<figure>
      <img src="images/giftest.gif" alt="UI">
      <figcaption><b>Figure 4</b>: Figure with image</figcaption>
</figure>


<img src="images/giftest.gif" alt="UI">
<b>Figure 5</b>: Plain Image

## Embedded images

My text ![UI](images/ui.png){style="width:4%"} .

## ![UI](images/ui.png){style="width:10%"}  My header.

My text ![UI](images/ui.png){style="width:4%"} .

## ![UI](images/execute_all_default.svg){style="width:10%"}  My header.



## Code blocks

<pre style="margin: 15px 0">
    <code style="white-space: pre; padding: 10px; box-sizing: border-box;">
myCode
  </code>
</pre>

<pre style="margin: 15px 0">
<code style="white-space: pre; padding: 10px; box-sizing: border-box;">
myCode
</code>
</pre>

<pre style="margin: 15px 0">
    <code style="white-space: pre; padding: 10px; box-sizing: border-box;">from shift.core import files
workflow, catalog_manifest = files.openBatchWorkflow("&ltpath_to_your_workflow_file&gt")</code>
</pre>