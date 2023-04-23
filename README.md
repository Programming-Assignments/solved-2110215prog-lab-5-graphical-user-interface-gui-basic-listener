Download Link: https://assignmentchef.com/product/solved-2110215prog-lab-5-graphical-user-interface-gui-basic-listener
<br>
<strong>Lab 5: Graphical User Interface (GUI) &amp; Basic Listener</strong>

<strong> </strong>

<h1>Instruction</h1>

<ol>

 <li>Click the provided link on CourseVille to create your own repository.</li>

 <li>Open Eclipse and then “File &gt; new &gt; Java Project” and set project name in this format</li>

</ol>

<strong>2110215_Lab5_2021_1_{ID}_{FIRSTNAME}</strong>

<ul>

 <li>Example:<strong> 2110215_Lab5_2021_1_6337492021_Jirapash</strong>.</li>

</ul>

<ol start="3">

 <li>Initialize git in your project directory ○ <strong>Add .gitignore. </strong>

  <ul>

   <li>Commit and push initial codes to your GitHub repository.</li>

  </ul></li>

 <li>Implement all the classes and methods following the details given in the problem statement file which you can download from CourseVille.

  <ul>

   <li><strong>The provided files contain two folders: </strong>src<strong> and </strong>res<strong>. make sure to add both into your project. (And use both of them as Source Folder)</strong></li>

  </ul></li>

</ol>

○ You should create commits with meaningful messages when you finish each part of your program.

○ You don’t need to wait until you finish all features to create a commit.

<ol start="5">

 <li>Export your project into a jar file called <strong>Lab5_2021_1_{ID}</strong> and place it at the root directory of your project.

  <ul>

   <li>Example: <strong>jar</strong></li>

  </ul></li>

 <li>Push all other commits to your GitHub repository</li>

</ol>




<strong> </strong>

<h1>1. Problem Statement: Harvest Simulator</h1>

<strong> </strong>

<strong> </strong>

With the economic crisis, CPShop had to be closed. With a little of money left, the manager of the shop chooses to return to his hometown in a countryside and back to the good old way of life of his parents — agriculture. He knows you who is a programmer and he want to run a simulation on income gain from harvest crops he planted. Also, he takes very good care of his crops so they never wither.




<strong>Harvest Simulator </strong>

<strong>            </strong>This is a simulation program for calculating income from each harvest. The manager has some programming knowledge so the program is partially done. He asks you to complete it for him. You need to understand JAVAFX and EVENT-HANDLER in order to complete this assignment.




<h2><em>Figure 1: The initial GUI of the application </em></h2>




The GUI can be divided into TWO parts Control part on the left and Field part on the

right.




<strong>             </strong>

<h2>Control part</h2>

This is a part to select an item, be it a seed or the removal tool, show current money and button for simulating each harvest. For a seed, it is used to plant in the field. For the removal tool, it is used to remove a plant in the field.




<h3><em>Figure 2: The GUI of the Control part </em></h3>

The selected item will be highlighted if clicked when you have enough money for it. If you choose another item that you can afford, the newly clicked item will be highlighted instead.

NO MORE THAN ONE ITEM WILL BE HIGHLIGHTED AT THE SAME TIME.

After planting a crop, if money reduced from buying a seed is less than selected item price, the item will be unselected and unhighlighted. If you hover mouse over an item button, the tooltip of that item will be shown for item information




<em>Figure 3: The GUI of the Control part when selected an item and hovering mouse over an item </em><strong>Field part </strong>

<strong> </strong>This part represents the field with space to plant crops. When clicking a field cell while selecting an item, an action will be done according to item selected.

<strong>             </strong>

<strong> </strong>

<h3><em>Figure 4: The GUI of the Field part </em></h3>

<em> </em>




JavaFX Install and Project Setup (If you have not done so). Please set the command line argument correctly (shown next page!)

In this assignment, you need to use JavaFX version 11 -15 in order to run the project and do this assignment.

If you don’t have any JavaFX, you can get the latest version from <a href="https://gluonhq.com/products/javafx/">https://gluonhq.com/products/javafx/</a>

Please download the latest release SDK of your OS version.




Once the download complete, extract the file then move the extracted folder to somewhere that you think it is easily accessible.

The recommended location is “C:Program FilesJava”




To add JavaFX to the eclipse project, follow these steps.

<ol>

 <li>Right-Click your project &gt; Build Path… &gt; Configure Build Path</li>

 <li>In the Libraries Tab, under Classpath, click <strong>Add External JAR…</strong></li>

</ol>




<ol start="3">

 <li>Navigate to the previously extracted JavaFX folder, go to the folder <strong>lib</strong>, and select every file in there and click Open.</li>

</ol>







Your Libraries should look like this.

Then, you need to modify <strong>Run Configurations</strong>.

This can be done by right-clicking Main.java &gt; Run As &gt; Run Configurations… Under Arguments tab, in the VM arguments section, place this command in

For Windows

–module-path “Path to your JavaFX folderlib” –add-modules javafx.controls,javafx.graphics,javafx.media,javafx.fxml

For Mac

–module-path “Path to your JavaFX folderlib” –add-modules javafx.controls,javafx.fxml




Afterwards, click Run and you will be able to run the program from now on.<strong>                                                  </strong>

<ol start="2">

 <li><strong> Implementation Details: </strong></li>

</ol>

There are six classes to be completed or be created if not exist: <strong>Main</strong>, <strong>ControlPane, ItemPane</strong>,<strong> ItemButton, FieldPane and FieldCell</strong>. There are already two classes provided: <strong>Item</strong> and <strong>SimulationManager</strong>. Your program can have more private methods/fields than specified in this instruction.




Tip: Use Ctrl+Space or auto-complete/suggestion feature will help you a lot. You can configure the key by going to Window -&gt; Preference -&gt; General -&gt; Keys and search for content assist.

<em>* Noted that Access Modifier Notations can be listed below <strong>             </strong></em>

<strong><em>+ (public)          </em></strong>

<strong><em># (protected)     – (private) static </em></strong><em>will be underlined. <strong>abstract </strong>will be italic.</em>

<strong> </strong>

<h2>2.1 Class Item</h2>

This class represents items or tools in ItemButtons and crops when referred in FieldCells. This class is already provided. There is a destroy tool item for removing crops in FieldCells.

<h3>2.1.1 Field</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="312">– String itemName</td>

   <td width="312">The name of the item.</td>

  </tr>

  <tr>

   <td width="312">– String url</td>

   <td width="312">The url of the item’s image.</td>

  </tr>

  <tr>

   <td width="312">– int price</td>

   <td width="312">Price of the item.</td>

  </tr>

  <tr>

   <td width="312">– int income</td>

   <td width="312">Income of the crop when the item is used to plant the crop in FieldCells.</td>

  </tr>

 </tbody>

</table>

<h3>2.1.2 Constructor</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="291">+ Item ( String itemName )</td>

   <td width="333">Initializes each field according to the itemName parameter.</td>

  </tr>

 </tbody>

</table>

<h3>2.1.3 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="215">+ boolean isDestroyTool ( )</td>

   <td width="409">Return true if this item is the destroy tool.</td>

  </tr>

  <tr>

   <td width="215">+ String getPriceText ( )</td>

   <td width="409">Return price String to be used in tooltip</td>

  </tr>

  <tr>

   <td width="215">+ String getIncomeText ( )</td>

   <td width="409">Return income String to be used in tooltip</td>

  </tr>

  <tr>

   <td width="215">+ void getter for each field</td>

   <td width="409"></td>

  </tr>

 </tbody>

</table>




<strong> </strong>

<h2>2.2 Class ItemButton extends Button</h2>

<strong>    </strong>

<em>Figure 8: Left: Unhighlighted ItemButton, Right: Highlight ItemButton</em>

<h3>2.2.1 Field</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="185">– Item item</td>

   <td width="439">Item in this button.</td>

  </tr>

 </tbody>

</table>

<h3>2.2.2 Constructor</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="167">+ ItemButton( String itemName )</td>

   <td width="457">/* Fill Code */Initializes the ItemButton with the following specification:–                      Set the inset padding to 5.–                      create a new item with itemName and set it to the item field.–                      Set the Graphic (icon) with the ImageView which has to create an Image that use String url of the item and set ImageView fit width and height to 48.–                      Background and Border are already provided.–                      Set tooltip by calling provided setTooltip() method.</td>

  </tr>

 </tbody>

</table>

<h3>2.2.3 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="187">+ void highlight ( )</td>

   <td colspan="2" width="437">/* Fill Code */Set its <strong>Background </strong>to be <strong>filled </strong>with <strong>LIMEGREEN </strong>color</td>

  </tr>

  <tr>

   <td width="187">+ void unhighlight ( )</td>

   <td colspan="2" width="437">/* Fill Code */Set its <strong>Background </strong>to be <strong>filled </strong>with <strong>WHITE </strong>color</td>

  </tr>

  <tr>

   <td width="187">+ Item getItem ( )</td>

   <td colspan="2" width="437">/* Fill Code */A getter for item</td>

  </tr>

  <tr>

   <td width="187">– void setTooltip( )</td>

   <td colspan="2" width="437">Set the tooltip of the button to show information of item in this button when hovering mouse over the button.</td>

  </tr>

  <tr>

   <td colspan="2" width="594">* ItemButton’s onAction ( ) will be implemented by another class for controlling highlight of</td>

   <td width="30"></td>

  </tr>

  <tr>

   <td width="187"></td>

   <td width="407"></td>

   <td width="30"></td>

  </tr>

 </tbody>

</table>

many ItemButtons.

<strong> </strong>

<h2>2.3 Class ItemPane extends GridPane</h2>

<strong> </strong>

<em>Figure 8: Picture of ItemPane</em>




<h3>2.3.1 Field</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="257">– ObservableList&lt;ItemButton&gt; itemButtonList  </td>

   <td width="367">Collects all ItemButton in this pane.</td>

  </tr>

 </tbody>

</table>

<h3>2.3.2 Constructor</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="252">+ ItemPane ( )</td>

   <td width="373">/* Fill Code */Initializes the ItemPane.–                      Sets the alignment of the pane to the <strong>CENTER </strong>– Sets both <strong>vertical gap</strong> and <strong>horizontal gap</strong> to 10 – Instantiates <strong>six</strong> ItemButtons:<em>“Corn”</em>, <em>“Coffee”</em>, <em>“Blueberry”</em>, <em>“Strawberry”</em>,<em>“Pineapple”</em>, and <em>“DestroyTool” </em>–                      Implement and set setOnAction of each ItemButtonto do setSelectedButton()if money inSimulationManager is equals to or more than price of Item in ItemButton.<strong>HINT</strong>: See how to write EventHandling at page 56 inGUI lecture slide–                      Add ItemButtons to each cell. There are two rows with three columns each in GridPane.</td>

  </tr>

 </tbody>

</table>




<h3>2.3.3 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="257">+ void setSelectedButton(ItemButton selectedItemButton)</td>

   <td width="367">/* Fill Code */This method sets selectedItemButton of SimulationManager to match the parameter, resetButtonsBackGroundColor() and  then</td>

  </tr>

  <tr>

   <td width="257"></td>

   <td width="367">highlight() the selected one which is the parameter.</td>

  </tr>

  <tr>

   <td width="257">+ voidresetButtonsBackGroundColor()</td>

   <td width="367">/* Fill Code */This method unhighlight() each button in itemButtonList</td>

  </tr>

 </tbody>

</table>




*You can find GridPane’s documentation here: <a href="https://docs.oracle.com/javase/8/javafx/api/javafx/scene/layout/GridPane.html">https://docs.oracle.com/</a><a href="https://docs.oracle.com/javase/8/javafx/api/javafx/scene/layout/GridPane.html">javase</a><a href="https://docs.oracle.com/javase/8/javafx/api/javafx/scene/layout/GridPane.html">/8/javafx/api/javafx/scene/layout/GridPane.html</a>  And how to use GridPane here:  <a href="http://tutorials.jenkov.com/javafx/gridpane.html">http://tutorials.jenkov.com/javafx/gridpane.html</a><a href="http://tutorials.jenkov.com/javafx/gridpane.html">  </a>

<strong> </strong>

<h2>2.4 Class ControlPane extends VBox</h2>




<em>Figure 9: The outline showing how the ControlPane is constructed</em>




<h3>2.4.1 Field</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="312">– ItemPane itemPane</td>

   <td width="312">ItemPane in this ControlPane</td>

  </tr>

  <tr>

   <td width="312">– Label moneyLabel</td>

   <td width="312">Label to show current money.</td>

  </tr>

  <tr>

   <td width="312">– Button harvestButton</td>

   <td width="312">Button that triggers each harvest and increase money.</td>

  </tr>

 </tbody>

</table>

<h3>2.4.2 Constructor</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="164">+ ControlPane ( )</td>

   <td width="460">/* Fill Code */Initializes the ControlPane.–                      Set the alignment of the pane to the <strong>CENTER</strong> – Set the preferred width to 300.–                      Set the spacing to 15.–                      Set filllWidth to true.–                      Border is already provided.–                      Instantiates each node and set to fields:●       moneyLabel is a label with font size 20 and set the text by setMoneyText().●       A Label with text “Please select a seed or removal tool” and font size 14●       itemPane is an ItemPane.●       harvestButton is a Button with the text “Harvest” and has a width of 150 and setOnAction to</td>

  </tr>

  <tr>

   <td width="164"></td>

   <td width="460">harvestButtonHandler()– Adds each node to the pane’s children in the correct order.</td>

  </tr>

 </tbody>

</table>

<h3>2.4.3 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="246">+ void setMoneyLabelText()</td>

   <td width="378">Set moneyLabel textProperty to “Money: ” + SimulationManager.getMoney()</td>

  </tr>

  <tr>

   <td width="246">+ Getter method for each field</td>

   <td width="378">/* Fill Code */</td>

  </tr>

 </tbody>

</table>




<h2>2.5 Class FieldCell extends Pane</h2>

This class represent a cell in FieldPane. It can contain a crop and is clickable to plant a crop while selected an ItemButton. It has tooltip to show the crop information while hovering mouse over it when there is crop in the cell.

<strong> </strong>

<em>Figure 11: A picture of a FieldCell with a crop while mouse is hovering over it.</em>




<h3>2.6.1 Field</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="233">– Item crop</td>

   <td width="391">Crop in this FieldCell.</td>

  </tr>

  <tr>

   <td width="233">– Tooltip tooltip</td>

   <td width="391">Tooltip of the FieldCell to show information of the crop in this FieldCell when hovering mouse over the FieldCell.</td>

  </tr>

 </tbody>

</table>




<h3>2.6.2 Constructor</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="185">+ FieldCell ( )</td>

   <td width="439">/* Fill Code */Initializes the FieldCell:–                      Set the preferred width and height to 48.–                      Set both <strong>min width</strong> and <strong>min height</strong> to 48.–                      Set the inset padding of 8.–                      Border is already provided.–                      Set the <strong>Background</strong> by calling setBackgroundSoilColor( ).–                      Set tooltip by calling provided setTooltip() method. – Complete the handle method in EventHandler given in the code.</td>

  </tr>

 </tbody>

</table>







<h3>2.6.3 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="252">+ void onClickHandler( )</td>

   <td width="373">/*Partially Provided*/This method is the handler when the cell is clicked. If there is a button selected in SimulationManager, do the following.If selectedItem is DestroyTool, set this FieldCell crop to null and call setBackgroundSoilColor( ).If it’s not the destroy tool and this Fieldcell doesn’t have a crop:–                      Set crop to selectedItem.–                      Reduce the money in SimulationManager. – Create new <strong>Image</strong> with selectedItem url and setBackgroundSoilColor(Image) with it – Set tooltip text with selectedItem name and selectedItem income text.</td>

  </tr>

  <tr>

   <td width="252">– void setBackgroundSoilColor( )</td>

   <td width="373">– Set the <strong>Background</strong> with <strong>BackGroundFill</strong> <strong>MOCCASIN</strong> Color</td>

  </tr>

  <tr>

   <td width="252">– voidsetBackgroundSoilColor(Image image)</td>

   <td width="373">— Set the <strong>Background</strong> with <strong>BackGroundFill</strong> <strong>MOCCASIN</strong>Color with image parameter background</td>

  </tr>

  <tr>

   <td width="252">– void setUpTooltip( )</td>

   <td width="373">Set up the tooltip of the FieldCell to show information of the crop in this FieldCell when hovering mouse over the FieldCell.</td>

  </tr>

  <tr>

   <td width="252">+ Item getCrop()</td>

   <td width="373">/* Fill Code */Getter for crop field.</td>

  </tr>

 </tbody>

</table>




*You can find Pane’s documentation here: <a href="https://docs.oracle.com/javase/8/javafx/api/javafx/scene/layout/Pane.html">https://docs.oracle.com/javase/8/javafx/api/javafx/scene/layout/Pane.html</a>

And a tutorial here: <a href="https://www.geeksforgeeks.org/javafx-pane-class">https://www.geeksforgeeks.org/javafx</a><a href="https://www.geeksforgeeks.org/javafx-pane-class">–</a><a href="https://www.geeksforgeeks.org/javafx-pane-class">pane</a><a href="https://www.geeksforgeeks.org/javafx-pane-class">–</a><a href="https://www.geeksforgeeks.org/javafx-pane-class">class</a>

Pane class is a base class for layout panes like GridPane, Hbox, StackPane and TilePane so it’s very plain.

<h2>2.6 Class FieldPane extends GridPane</h2>

This class represent the field for planting crops and partially provided. It contains FieldCells which is slot for planting crops.




<em>Figure 10: Picture of FieldPane with some crops in FieldCells.</em>




<h3>2.5.1 Field</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="316">– ObservableList&lt;FieldCell&gt; fieldCells</td>

   <td width="308">JavaFX’s observable list, which can be used for storing the fieldCells to display on field.</td>

  </tr>

 </tbody>

</table>

<h3>2.5.2 Constructor</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="209">+ FieldPane()</td>

   <td width="415">/* Fill Code */Initializes the FieldPane.–                      Set the preferred width to 500.–                      Set the alignment of the pane to the <strong>CENTER</strong> – Set both <strong>vertical gap</strong> and <strong>horizontal gap</strong> to 8.–                      Set the inset padding of 8.–                      Border is already provided.–                      Set the <strong>Background</strong> with <strong>BackGroundFill</strong> <strong>LIMEGREEN</strong> Color – Create and add 6*8 FieldCells to fieldCells field and add to this child in 6 rows * 8 columns.</td>

  </tr>

 </tbody>

</table>

<h3>2.5.3 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="235">+ int calculateIncome ( )</td>

   <td width="389">/* Fill Code */Calculate total income from each FieldCell in fieldCells if that cell contains a crop.</td>

  </tr>

 </tbody>

</table>




* ObservableList is a list that enables listeners to track changes when they occur.

You might need it in your term project so you can read more about it here:

<a href="https://docs.oracle.com/javafx/2/collections/jfxpub-collections.htm">https://docs.oracle.com/javafx/2/collections/jfxpub</a><a href="https://docs.oracle.com/javafx/2/collections/jfxpub-collections.htm">–</a><a href="https://docs.oracle.com/javafx/2/collections/jfxpub-collections.htm">collections.htm</a>

<h2>2.7 Class SimulationManager</h2>

This class contain reference and control over some part of the simulation. This class is already provided.

<h3>2.7.1 Field</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="312">– ItemButton <u>selectedItemButton</u></td>

   <td width="312">Selected ItemButton.</td>

  </tr>

  <tr>

   <td width="312">– ControlPane <u>controlPane</u></td>

   <td width="312">An instance of ControlPane</td>

  </tr>

  <tr>

   <td width="312">– FieldPane <u>fieldPane</u></td>

   <td width="312">An instance of FieldPane</td>

  </tr>

  <tr>

   <td width="312">– int money</td>

   <td width="312">The money at the start of the program is set 500.</td>

  </tr>

 </tbody>

</table>

<h3>2.7.3 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="256">+ void harvestHandler ( ) </td>

   <td width="368">This is handler function for the harvest button. This method increase money by calling ControlPane’s calculateIncome().</td>

  </tr>

  <tr>

   <td width="256">+ void reduceMoneyBuySeed ( )</td>

   <td width="368">This method is called when a crop is planted in a FieldCell to reduce the money by that crop price, update moneyLabel’s text and unselect ItemButton if money left is less than selecting Item price.</td>

  </tr>

  <tr>

   <td width="256">+ setters and getter for each field as needed</td>

   <td width="368"></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<h2>2.8 Class Main extends Application</h2>

<h3>2.9.1 Method</h3>

<table width="624">

 <tbody>

  <tr>

   <td width="252">+ void start ( Stage primaryStage )</td>

   <td width="372">/* Fill Code */The main entry point of the JavaFX application. This method should:–                      Creates a root container using HBox with spacing between containing pane of 10 and an inset padding of 10.–                      Set its preferred height to 400px.–                      Initializes ControlPane and FieldPane and add them to the root container.–                      Set SimulationManager’s ControlPane and FieldPane.–                      Create a scene with root container.–                      Set primaryStage with appropriate scene and title <em>“Harvest Simulator”</em>.–                      Set the stage window size to match the scene.–                      The stage window must not be resizable.–                      Show the primaryStage.</td>

  </tr>

  <tr>

   <td width="252"><u>+ void main ( String [] args )</u></td>

   <td width="372">An entry point of the application.</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>


