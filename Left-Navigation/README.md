**leftnav-ul.vm**

* Creates an unordered list with links to Pages, Folders, References, and External Links. Any of those assets can be excluded at the Block level or the Format level (using xpath).
* It assumes that each Folder has a landing page. Landing page is excluded by default.
* Takes into account a check for Title and Display Name and uses System Name as a fallback if neither are available.
* On the Index Block:
    * Index Folder (optional)
    * Depth of Index should be at least 1 (will create nested lists automatically based on depth provided)
    * Indexed Asset Types of Pages and Links
    * Rendering Behavior of "Render normally"
    * Do not include Page XML (is not needed and will increase block size)
    * Indexed Asset Content for Regular Content (asset link) and User Metadata (access to metadata values)