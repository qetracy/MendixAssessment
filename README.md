# MendixAssessment

# Build Your First Mendix App

## 1  Introduction
Mendix is a low-code application development platform that allows you to develop mobile and web apps. This document explains how to create a basic Mendix app that stores stock data from a hardware store.

Note: These instructions are to be followed in [**Design mode**](https://docs.mendix.com/refguide/page/#design-mode). The app is automatically set to **Structure Mode**, so to set it to **Design mode**, go to **Edit** > **Preferences** > **Work environment** > **Design mode** > **OK**.

Create a home page that will direct the user to a grid that stores the hardware stock data. To extend this new functionality, add a [building block](https://docs.mendix.com/refguide/building-block/) to the **Home_Web** page. This will allow you to navigate easily between the two pages without needing to style the page. To add a building block, follow these steps:

1. In the **App Explorer**, open **MyFirstModule** > **Home_Web**
2. In the right column, select **Toolbox** > **Building blocks**
3. Navigate down to **Cards**
4. Select the **Card action** element  and drag it onto the **Home_Web** page
5. Double-click the **Card Action** text in the **Caption** box, rename the element “Tools”=
6. Click **OK**

## 2  Configure the Home Page
Create a home page that will direct the user to a grid that stores the hardware stock data. To extend this new functionality, add a building block to the **Home_Web** page. This will allow you to navigate easily between the two pages without needing to style the page. To add a building block, follow these steps:

1. In <![endif]--> the **App Explorer**, open **MyFirstModule** > **Home_Web**
2. In the right column, select **Toolbox** > **Building blocks**
3. Navigate down to **Cards**
4. Select the **Card action** element  and drag it onto the **Home_Web** page
5. Double-click the **Card Action** text in the **Caption** box, rename the element “Tools”
6. Click **OK**

### 2.1 Change the Tools Button
The Card Action building block automatically creates a link that brings the user to the data grid with the store’s hardware stock. Change the link to a button to help the user find it more easily. To do this, follow these steps:

1.	Right-click the blue < link and select **Properties**
2.	Under **General**, select **Button** > **Button style** > **Info**
3.	Click **OK**

## 3  Add an entity
The hardware store’s stock information is displayed in an [entity](https://docs.mendix.com/refguide/entities/). An entity is typically a singular, identifiable object in the real-world. To add an entity, follow these steps:

1. In the **App Explorer**, open **MyFirstModule** > **Domain model**
2. In the top left corner, click **Entity.**
3. Double-click the blue entity box and under **General**, rename the entity “Tools”
4. Click the **Attributes** tab to add two attributes
a. Click **New**
b.  Under **Common**, rename the attribute “Name"
c. Under **Type**, select **String** 
d. Click **OK** > **New**
f. Under **Common**, rename the attribute “Code”
g. Under **Type**, select **Integer**
h. Click **OK** > **OK**

## 4  Create an Overview Page and Data Grid
A [data grid](https://docs.mendix.com/refguide/data-grid/) is where the tool information is stored in a table format. To create a data grid, follow these steps:

1.  In the **App Explorer**, right-click **MyFirstModule** > **Add**
2.  In the left column, select **Blank** > **Blank Page Template**
3.  Click **OK**
4. Right-click the new **Page** > **Rename** and rename it “Tools_Overview”
5.  Click **OK**

On the **Tools_Overview** page:

1. Open the **Toolbox** and click **Widgets**
2. Under **Data containers**, select **Data grid** and drag it onto the blank page

Configure the data grid to input the information stored in the **Tools** entity:

1. Right-click the **Data grid** > **Select entity**
2. Under **MyFirstModule**, select the **Tools** entity and click **Select**
a. This will create a data source popup. Make sure **Database** is selected before proceeding.
3. Click **OK**

### 4.1 Fix the Data Grid 
Change the data grid settings to improve page position and UX. To do this, follow these steps:

1.	Open **Home_Web** and right-click inside the data grid and select **Properties**
2.	Under **General**, click the **Selection mode** dropdown and select **Multi-selection**
3.	Click **Appearance**
4.	Under **Design properties**, click the **Spacing top** dropdown and select **Outer large**
a.	 Repeat this step on the **Spacing left** dropdown
5.	Click **OK**

## 5  Configure the Home and Tools Page
 
Once both pages have been created, link them together by following the steps below:
1. Open **Home_Web** and right-click the blue > button on the far-right side of the page
2. Select **Edit on click action**
3. Under **On click**, select **Show a page** > **MyFirstModule**> **Tools_Overview**
4. Click **Select** > **OK**

## 6  Configure the Grid Buttons  
Configure the data grid buttons to create a popup page where you can enter tool information. This will generate a page that will allow you to add and edit tool information in your hardware stock. To configure the buttons, follow these steps:

**New** button:

1. On **Tools_Overview**, right-click **New** > **Generate** **Page**
2. Under **Forms**, select **Form Columns**
3. Click **OK**
a. This will create a page called “Tools_NewEdit”
4. Right-click the new **Page** > **Rename** and rename it “Add_Tools”
5. Click **OK**

**Edit** button:

1. On the **Tools_Overview** page right-click **Edit** > **Generate on-click page**
2. Under **Forms**, select **Form Columns**
3.  Click **OK**
    a. This will create a page called “Tools_View"
a. This will create a page called “Tools_View"
4 .Right-click the new **Page** > **Rename** and rename it “Edit_Tools”
5. Click **OK**

## 7  Create a Custom Save Button Message 
Create a custom message that appears when you add a tool and save it to the data grid. This is done by creating a microflow that validates the data being inputted into the data grid. To create a custom message, follow these steps:

1. In the **App Explorer**, open **MyFirstModule** > **Add_Tools**
2. Right-click **Save** > **Generate validation microflow**
3. Rename the microflow “Save_Message” and click **Generate microflow** > **Open the microflow**
a. Navigate down on the page to view the microflow
4. In the **Toolbox**, under **Client Activities**, select **Show Message** and drag it onto the microflow between the **Close Page** and **End event** notations
5. Double-click the **Show Message** microflow and in **Template**, type the message “Tool saved successfully”
6. Click **OK**
7. Repeat steps 1-7 for the Edit_Tools page and rename it “Save_Message_2”
