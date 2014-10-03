The Form Builder is meant to allow users to easily setup their own forms and with an intermediate amount of knowledge of Velocity or XSLT be able to have user entered Form results be emailed, stored as an Excel file, or stored as a Page within Cascade Server.

Before users can create Forms, it is necessary to setup the Content Type for the Form pages. The following instructions are meant to be a guide on setting up the Content Type and making all necessary modifications to existing code to allow for web services calls to be utilized. Once the following Content Types are setup, users should not have to go through these steps again.

## Overview of Components

- **Form Content Type** - The actual Page with customizable form field information. The Form will be Published and should have .php extension designated on its Configuration.
- **Form Config** - The Block that has CMS information that will be utilized by web service calls when handling results from users entering content into the published Form. The *Authentication File Path* should point to a PHP file on the web server that contains a valid username and password to be used for the Web Services calls. This is used as a way of separating secure information from the published Form. It is strongly recommended that the Form Config block be saved in a location only Writable to people who are allowed access to the Web Services information. 
- **Optional Results Content Type**

### Form Content Type

- [Form Data Definition.xml](https://github.com/hannonhill/Velocity-Cookbook/tree/master/PHP-Form-Builder/form/form-data-definition.xml) (Data Definition)
- [form-display.vm](https://github.com/hannonhill/Velocity-Cookbook/tree/master/PHP-Form-Builder/form/form-display.vm) (Velocity Format)

### Form Config

- [Form Config Data Definition.xml](https://github.com/hannonhill/Velocity-Cookbook/tree/master/PHP-Form-Builder/form-config/form-config-data-definition.xml) (Data Definition)
- Sample authentication file content:
```
<?php
$auth = array(
    "username" => "user",
    "password" => "pass"
);
?>
```

### Optional Results Content Type

- [Generic Results Data Definition.xml](https://github.com/hannonhill/Velocity-Cookbook/tree/master/PHP-Form-Builder/results/generic-results-data-definition.xml) (Data Definition)
- [generic-result.vm](https://github.com/hannonhill/Velocity-Cookbook/tree/master/PHP-Form-Builder/results/generic-results.vm) (Velocity Format)
- [Custom Results Data Definition.xml](https://github.com/hannonhill/Velocity-Cookbook/tree/master/PHP-Form-Builder/results/custom-results-data-definition.xml) (Data Definition Example: will need to be modified based on form)
- [custom-results.vm](https://github.com/hannonhill/Velocity-Cookbook/tree/master/PHP-Form-Builder/results/custom-results.vm) (Velocity Format Example: will need to be modified based on form)

## Creating the Form Content Type

1. Create a **Configuration Set** that utilizes the **Template** with the page layout that you would like your Form to have. The **Configuration/Output** will need to have the output extension .php set.
2. Assign a **Calling Page block** and the **Format** included to the Region in your Configuration that you would like your form content placed.
3. Create a **Data Definition** utilizing the included **Form Data Definiton.xml** file. The XML can be pasted straight into your new Data Definition by clicking the XML tab on the Data Defintion.
4. Create a **Content Type** for your Forms, assigning the **Configuration Set** that you just created to your new Content Type.

## Creating the Form Config Block

1. Create a **Data Definition** utilizing the included **Form Config.xml** file. The XML can be pasted straight into your new Data Definition by clicking the XML tab on the Data Defintion.
2. Create a **Block** for your Form Config, assigning the **Data Definition** that you just created to your new Block.

## Storing Results as Pages

If you are wanting the results users entered into your Form to be stored as a Page within Cascade, you will need to also setup a Content Type for that content to be saved. This is not necessary if you only want your form results emailed or stored into an Excel file. A common use for this has been allowing users to enter comments and have each of those results automatically create a comment page within Cascade.

There are two types of Content Types that you can utilize to store your results. One is a Generic Results Content Type and the other is a Custom Results Content Type. The only difference between these two ways of having your results stored is the Data Definition fields that your results gets saved into and the Format that handles the display of those results (Data Definition content).

The Generic Results Data Definition.xml is included and an example of the Custom Results Data Definiton.xml has been included. If you choose to use a Custom Results Content Type, there will be some necessary modifications to the Data Definition and Format based on your Form. It is strongly recommended that you begin with using the Generic Results Content Type and then when you are comfortable with all of the connections being made, try utilizing the Custom Results Content Type for more robust use of forms within your sites.

The below steps explain how that Content Type should be setup.

### Creating the Form Results Content Type

1. Create a **Configuration Set** that utilizes the **Template** with the page layout that you would like your Form Results to have.
2. Assign a **Calling Page block** and the **Format** included to the Region in your Configuration that you would like your Form Results content placed.
3. Create a **Data Definition** utilizing the included **Form Results.xml** file. The XML can be pasted straight into your new Data Definition by clicking the XML tab on the Data Defintion.
4. Create a **Content Type** for your Form Results, assigning the **Configuration Set** that you just created to your new Content Type.

#### Further Explanation of the Generic Form Content Type

If you look at the Generic Results Data Definition.xml, you will notice that there is a Group which contains a text field and a text box. Multiple groupings can be added to the page. When a user fills out the Form, each form field's identifier will be saved in the text field and the result will be saved in the corresponding textbox.

The format provided will iterate through these groupings and output the "identifier: result."

#### How to Modify the Custom Results Content Type

By selecting to have Custom Result pages created when users enter content into your Form, you are allowing for more flexibility of how that content can later be reused across pages.

The Custom Results Data Definition is basically a recreation of the Form that users will be using to submit content. Those fields will need to be recreated in a Data Definition so that the content has a way of being stored and viewed within Cascade. You will need to create a one to one match of field types from your Form to your Custom Results Data Definition. The **Identifier** for each of your Data Definition fields will need to be the same as the Name field for your corresponding Form fields. Please note: If there is a space in the Name field of your Form, this should be replace with an underscore (_) in the corresponding Identifier of your Data Definition.

A sample of a Form has been included with the corresponding Data Definition and Velocity Format. The Velocity Format is a basic Format that simply outputs the content of the Data Definition. This format can be written using Velocity or XSLT, any valid HTML can be wrapped around the resulting content as necessary. Once the Data Definition is written to match the Form, the rest is handled like any other Page within Cascade Server.

## How to Use the Form Config Block (Once it's a Block)

1. **Create/Edit** the block.
2. **"Cascade Server URL (If adding a file to Cascade)"** will need to be filled in if Form results will be Saved as a Page or Excel file within Cascade Server. The `http(s)://` should be included as well as the `PORT` if applicable.
3. The **"Authentication File Path"** field should contain the path to a file containing a valid username and password for a User with Site Administration permissions to the Site that will have results files saved to it.
4. **"Site Name"** will need to be filled in
5. **"Content Type Path"** will need to be filled in if the Form results will be saved as a Page within Cascade Server. This designates what Page type the results pages should be when automatically created within Cascade Server. This field should contain the "Site Name:Content Type Path" for the designated Content Type. An example of this would look like, "example.edu:News Form Submission" if the Site name in Cascade Server is "example.edu" and the Content Type that results pages will have is "News Form Submission."

## How to Use the Form Builder (Once it's a Page)

1. **Create/Edit** the page.
2. **"Results"** is how the form's input will be handled. Form results can be emailed (send-email), saved to an Excel file within Cascade Server (save-to-excel), and/or saved as page content within Cascade Server (save-to-cms). The related fields for each of these options will need to be filled in depending on how results are to be handled.
3. The **"IF saving results to CMS"** refers to whether results should be saved as a page within Cascade Server and/or as a Excel file within Cascade Server
    1. **"Configuration"** is the block that contains secure information utilized for handling the results from the form. This is how the proper Config Block (discussed above) should be associated to the Form.
    2. **"Choose a file in the folder in which you want to save the file."** is utilized for detemining where the automatically generated results file(s) should be stored within the designated site. The file chosen will NOT be modified.
    3. **"Enter file name to be saved"** is used for naming the automatically generated results file(s).
        - The Excel file will be saved as `filename.csv`. If `filename.csv` already exists due to a previous form entry, results will be saved in the next row within that file. This file can then be downloaded from Cascade Server. The user can then import the file into Excel.
        - Pages created will be saved as `filename`. If `filename` already exists, the new file will become `filename1` then the next one will be `filename2` and so on.
4. The **"IF results are to be Emailed"** section is only necessary if results from the form should be emailed.
    1. **"Email address from which the emails will be sent"** is the address emails with the result content will be displayed as being sent from. This field can be useful for setting up email filters to group emails together from the same form. This is necessary if results are to be emailed.
    2. **"Email Subject (Title)"** will be the Subject line of the resulting email.
    3. **"Email Address to receive the results"** is where the results will be sent. One or more addresses can be provided as a comma-separated list.
5. **"Form Instructions"** is the intro text to the form.
6. Each **"Form Item"** group is a form element (text box, checkboxes, etc.)
7. The form items can be any of the following "form types":
    - **text** - one line text field
    - **textarea** - multiline text field
    - **password** - password protected text field
    - **dropdown** - dropdown menu
    - **checkbox** - checkbox options
    - **radio** - radio buttons
    - **hidden** - hidden field
    - **paragraph** - arbitrary paragraph text
8. **"Name"** is the name of the field as well as it's label.
8. **"Label"** can be provided if you wish to display more user-freindly text for the field's label.
9. **"Default Value"** will be used to pre-populate text fields. Non-text fields will default this value to checked for chckbox/radio fields and selected for dropdown fields.
10. For Dropdowns, Checkboxes, and Radio buttons, you must put in values in the **"Value"** text boxes. Make sure one of these Values matches the value entered into the Default Value field if you wish to have one of these checked/selected by default.
11. **"Content"** will be used to populate content for paragraph fields.
12. **"Required Field"** makes this form item required.
13. To add another field, press the + at the top left of the **"Form Item"** group box.
14. If you have **"Send E-mail"** checked to send the results, fill out the Email Addresses you'd like to send it to.
15. **"Submit Button Text"** is the text on the submit button on the form.
16. **"Form Confirmation Text"** is the text that will display for users once they have successfully submitted the form.
