
---

<p style="text-align:left;">

[< Main USD Tutorials Page](../usd#tutorials)
<span style="float:right;">
[Next Tutorial >](usd_tutorial_02.md)
</span>

</p>

---

## Creating a simple USD Stage

This tutorial is focused on creating a simple USD stage containing a transform and a sphere using the operators from Shift_USD catalog.


### Tutorial

1. Open Shift application. A new window's instance of Shift should appear like the following one:

<figure>
    <img src="images/usd_tutorial_01/step_01_t01.png" alt="Shift UI.">
    <figcaption><b>Figure 1</b>: Shift UI.</figcaption>
</figure>

>[!NOTE]
> Before creating the USD workflow, ensure that the USD nodes appear in the Node List widget. The catalogs combobox should show `sUSD` and `sUSDTypes` if USD is correctly loaded in Shift. If this is not the case, please check again the [Shift_USD installation page](../usd#installation).

2. Add a new *UsdStageNew* node to the board. Using the **Inspector** widget, set as the value for the **filepath** input plug the path to a `.usda` file. For the purpose of this tutorial, the filepath is: `D:/USD_TUTORIALS/01/HelloWorld.usda`. The board should look like the following:

<figure>
    <img src="images/usd_tutorial_01/step_02_t01.png" alt="Added the 'UsdStageNew' node to the board.">
    <figcaption><b>Figure 2</b>: Added the 'UsdStageNew' node to the board.</figcaption>
</figure>

3. Add a new *UsdPrimAdd* node to the board. Now, connect the **stage** output plug from the *UsdStageNew* node to the **stage** input plug of the new node. Also, set `/hello` as the value for the **primpath** input plug and choose `Xform` as the value for the **primType** input plug. Rename the node as *HelloXformAdd* to identify it easily. The board should look like the following:

<figure>
    <img src="images/usd_tutorial_01/step_03_t01.png" alt="Added the 'HelloXformAdd' node to the board for creating the Xform.">
    <figcaption><b>Figure 3</b>: Added the 'HelloXformAdd' node to the board for creating the Xform.</figcaption>
</figure>

4. Add another *UsdPrimAdd* node to the board for creating the geometry of the sphere. Connect the **stage** output plug from the *HelloXformAdd* node to the **stage** input plug of the new node.  Set `/hello/world` as the value for the **primpath** input plug and choose `Sphere` as the value for the **primType** input plug. Rename the node as *WorldSphereAdd* to identify it easily. The board should look like the following:

<figure>
    <img src="images/usd_tutorial_01/step_04_t01.png" alt="Added the 'WorldSphereAdd' node to the board for creating the sphere.">
    <figcaption><b>Figure 4</b>: Added the 'WorldSphereAdd' node to the board for creating the sphere.</figcaption>
</figure>

5. Finally, add a new *UsdStageSave* node. Connect the **stage** output plug from the *WorldSphereAdd* node to the **stage** input plug of the new node. A new filepath value can be set to save the file to another specified file. For the current example, leave the value empty to update the file created by the *UsdStageNew* node. The board should look like the following:

<figure>
    <img src="images/usd_tutorial_01/step_05_t01.png" alt="Added the 'UsdStageSave' node to the board for saving the stage.">
    <figcaption><b>Figure 5</b>: Added the 'UsdStageSave' node to the board for saving the stage.</figcaption>
</figure>

7. Once the nodes are connected and properly set, the generated workflow can be executed to generate the USD file. The workflow will be executed and the nodes will show a blue progress bar as they are evaluated. Once the workflow has been executed, the board should look like the following:

<figure>
    <img src="images/usd_tutorial_01/step_06_t01.png" alt="Workflow executed.">
    <figcaption><b>Figure 6</b>: Workflow executed.</figcaption>
</figure>


### Visualizing the Stage

Shift is shipped with native plugins to visualize and inspect the stage. They can be accessed from the *Usd* top menu:
* **USD Outliner**: Shows the user the stage hierarchy sourced from specific Usd nodes in the active board workflow.

* **USD Viewer**: Shows the stage in the Usd viewer sourced from specific Usd nodes in the active board workflow.

<figure>
    <img src="images/usd_tutorial_01/step_08_t01.png" alt="Shift USD Outliner and USD Viewer plugins.">
    <figcaption><b>Figure 7</b>: Shift USD Outliner and USD Viewer plugins.</figcaption>
</figure>

Also, the *usdview* tool shipped with USD is used to visualise and inspect the stage:

<figure>
    <img src="images/usd_tutorial_01/step_07_t01.png" alt="Visualisation of the generated stage.">
    <figcaption><b>Figure 8</b>: Visualisation of the generated stage.</figcaption>
</figure>


### Workflow Resources

The workflow corresponding to this tutorial can be found in the following path in the Shift installation folder: `<path_to_the_shift_installation_folder>/shift/examples/USD/tutorials/tutorial_01_creating_first_stage/tutorial_01.sft`.

---

<p style="text-align:left;">

[< Main USD Tutorials Page](../usd#tutorials)
<span style="float:right;">
[Next Tutorial >](usd_tutorial_02)
</span>

</p>

---