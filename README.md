# MendixAssessment

# Build Your First Mendix App

## 1  Introduction
Mendix is a low-code application development platform that allows you to develop mobile and web apps. This document explains how to create a basic Mendix app that stores stock data from a hardware store. 

Note: These instructions are to be followed in [**Design mode**](https://docs.mendix.com/refguide/page/#design-mode). The app is automatically set to **Structure Mode**, so to set it to **Design mode**, go to **Edit** > **Preferences** > **Work environment** > **Design mode** > **OK**.

## 2 Configure the Home Page
The home page is used to direct the user to the data grid that holds all the stock data. Remove all existing containers and columns from this page to create a blank workspace. To do this, follow these steps:

1. In the **App Explorer**, open **MyFirstModule** > **Home_Web**
2.	Right-click all existing columns and containers and select **Delete**

### 2.1 Add a header 
Add [building blocks](https://docs.mendix.com/refguide/building-block/) and [widgets](https://docs.mendix.com/appstore/widgets/) to **Home_Web** to create a labeled and structured page. These elements allow you to identify and navigate easily within the app without needing to style the page. Add a header building block to the page and fill out the text with your hardware store name and website information. To do this, follow these steps:

1. In the **App Explorer**, open **MyFirstModule** > **Home_Web**
2. In the right column, select **Toolbox** > **Building blocks** > **Headers** > **Heroheader**
3. Drag this widget onto the blank home page 
4. Right-click the ‘Header Title’ text > **Edit caption**
5. Rename the title using the name of your hardware store.
6. Right-click the ‘Supporting text’ text > **Edit caption**
7. Insert a short blurb about the tool stock that is listed on the site

### 2.2 Add a Widget
Add a layout grid below the header to separate the home page into 3 columns. 
1.	In the **App Explorer**, open **MyFirstModule** > **Home_Web**
2.	In the right column, select **Toolbox** > **Widgets**
3.	Under **Structure**, select **Layout grid** > **4,4,4**
- This adds a layout grid with 3 columns to the home 

### 2.3 Add a Card Action 
The **Card Action** building block automatically creates a link that brings the user to the data grid with the store’s hardware stock. Change the link to a button to help the user find it more easily. To do this, follow these steps:

1.	Select **Toolbox** > **Building blocks**
2.	Navigate down to **Cards** 
3.	Select the **Card action** element and drag it onto the leftmost column. Leave the remaining two columns empty. 
4.	Right-click the **Card Action** > **Edit caption** 
5.	Rename the **Card Action** to ‘View Hardware Stock’
6.	Click **OK**

### 2.4 Change the Card Action Button
Change the card action button to a more visually appealing button. 

1.	Right-click the blue chevron link and select **Properties**
2.	Under **General**, select **Button** > **Button style** > **Info**
3.	Click **OK**

### 2.5 Change the Container Background
Adjust the background of the container to match the page background. 

1.	Right-click the card action container and select **Properties**
2.	Select **Appearance** and under **Background color**, select **Background Primary**
3.	Click **OK**

## 3  Add an Entity
The hardware store’s stock information is displayed in an [entity](https://docs.mendix.com/refguide/entities/). An entity is typically a singular, identifiable object in the real-world. To add an entity, follow these steps:

1. In the **App Explorer**, open **MyFirstModule** > **Domain model**
2. In the top left corner, click **Entity**.
3. Double-click the blue entity box and under **General**, rename the entity 'Tools'
4. Click the **Attributes** tab to add two attributes
5. Click **New**
- Under Common, rename the attribute ‘Name’
- Under **Type**, select **String** 
- Click **OK**
6. Click  **New**
- Under **Common**, rename the attribute 'Code'
- Under **Type**, select **Integer**
7. Click **OK** > **OK**

## 4  Create a Data Grid
A [data grid](https://docs.mendix.com/refguide/data-grid/) is where the tool information is stored in a table format. To create a data grid, follow these steps:

1.  In the **App Explorer**, right-click **MyFirstModule** > **Add**
2.  In the left column, select **Grids** > **Grid**
3.  Click **OK**
4. Right-click the new **Page** > **Rename** and rename it 'Tools_Overview'
5.  Click **OK**

### 4.1 Add the Tool Entity to the Data Grid
Configure the data grid to input information stored in the **Tools** entity.

1. Right-click the **Data grid** and click **Select entity**
2. Under **MyFirstModule**, select **Tools** 
- This creates a data source popup. Make sure **Database** is selected before proceeding.
3. Click **OK**

## 5  Configure the Tools Page
Update the **Tools_Overview** page to improve the page layout, headers, and UX. To do this, follow these steps:

### 5.1 Update Headers

1.	Right-click the ‘Page header title’ text box
2.	Select **Edit Caption** and rename the header to ‘Hardware Stock’
3.	Click **OK**
4.	Right-click the ‘Supporting text’ text box and input the following blurb: ‘All tools and associated codes are listed below. Search through the grid, add new tools, and edit tools here.’
5.	Click **OK**

### 5.2 Fix UX and Grid Formatting 
1.	Right-click inside the data grid and select **Properties**
2.	Under **General**, click the **Selection mode** dropdown and select **Multi-selection**
3.	Click **Appearance**
4.	Under **Design properties**, click the **Spacing top** dropdown and select **Outer medium**
- Repeat this step on the **Spacing left** dropdown
5.	Click **OK**

### 5.3 Edit buttons 
Change the 4 data grid buttons to match the button on the home page. To do this, follow these steps:
1.	Right-click the button and select **Properties**
2.	Under **General**, select **Button** > **Button style** > **Info**
3.	Click **OK**

## 6  Link the Home and Tools Page
Once both pages have been created, link them together so data can be transferred to and from each page. To do this, follow the steps below:
1. Open **Home_Web** and right-click the blue button and select **Edit on click action**
2. Under **On click**, select **Show a page**
3. Under **Page**, click **Select** and select  **MyFirstModule** > **Tools_Overview**
4. Click **Select** > **OK**

### 6.1 Edit the Navigation Menu   
The left side of the page has a vertical navigation menu with a home page icon. Add a tool icon to this menu to link to the Tools_Overview page.  

1. Open App **‘TW-2309’** and select **Navigation**
2. Under **Menu**, click **New Item** and rename the item ‘Tools’
3. Under **On click**, select **Show a page** > **MyFirstModule** > **Tools_Overview**
4. Click **Select** > **OK**

### 7  Configure the Grid Buttons 
Configure the data grid buttons to create a popup page where you can enter tool information. This generates a page that allows you to add and edit tool information in your hardware stock. To configure the buttons, follow these steps:

1.	On **Tools_Overview**, right-click **New** > **Generate Page**
2.	Under **Forms**, select **Form Columns**
3.	Click **OK**
- This creates a page called ‘Tools_NewEdit’
4.	Right-click the new **Page** > **Rename** and rename it ‘Manage_Tools’
5.	Click **OK**

## 7  Create a Custom Save Message
Create a custom message that appears when you add a tool and save it to the data grid. This is done by creating a microflow that validates the data being inputted into the data grid. To create a custom message, follow these steps:

1.	In the **App Explorer**, open **MyFirstModule** > **Manage_Tools**
2.	Right-click **Save** > **Generate validation microflow**
3.	Rename the microflow ‘Save_Message’ and click **Generate microflow** > **Open the microflow**
- Navigate down on the page to view the microflow
4.	In the **Toolbox**, under **Client Activities**, select **Show Message** and drag it onto the microflow between the **Close Page** and **End event** notations 
5.	Right-click the **Show Message** microflow and in **Template**, type the message ‘Tool saved successfully’
6.	Click **OK**




