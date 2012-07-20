**breadcrumb-ul.vm**

* Creates an unordered list with links to Folders. It assumes that each parent Folder has a landing page.
* Takes into account a check for Display Name and System Name. You won't have to worry about whether or not certain Metadata Fields are filled out. It will fall back to the System Name of the asset if no Display Name is found.
* Assumes paired Index Block is using "Start at the current page and include its folder hierarchy."


**breadcrumb.vm**

* Creates a plain text breadcrumb with links to Folders. It assumes that each parent Folder has a landing page.
* Takes into account a check for Display Name and System Name. You won't have to worry about whether or not certain Metadata Fields are filled out. It will fall back to the System Name of the asset if no Display Name is found.
* Assumes paired Index Block is using "Start at the current page and include its folder hierarchy."