**sitemap.vm**

* Creates a nested unordered list with links to Page assets and titles of parent Folders. It nests subfolders with `<ul>` nodes completely inside of `<li>` nodes.
* Takes into account a check for Title, Display Name, and System Name. You won't have to worry about whether or not certain Metadata Fields are filled out. It will fall back to the System Name of the asset if no Title or Display Name is found.
* Uses HTML comments after each Page/Folder is output. It will output some information that can help debug which node is being looped over if needed.
* Expects Cascade Server version 6.10+ so if you're using a version prior to that, switch the `$_EscapeTool.xml()` call to a `$_SerializerTool.serialize()` call.
