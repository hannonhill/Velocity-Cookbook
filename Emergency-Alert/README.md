**Alert-Display.vm**

* Loops through an Index Block of all Emergency Alerts
* Checks if the Emergency Alert is "Active" and has not "Expired"
* Outputs Active Alert


**Alert-Page-Display.vm**

* Use this Format on the Alert Page itself to display Alert content


**Data-Definition.xml**

* Includes "Active" Toggle
* Includes Text Field for Alert Message


**Server-Side-Include.xml**

* Use this in your Template when declaring your `<system-region>`
* Attach the `Alert Index Block` and `Format.vm` in the `Internal View`
* For the `External View` - create a basic template with one region and attach the `Alert Index Block` and `Format.vm`
* Use the Publish location in the `path/to/alert` section of the `External View`
