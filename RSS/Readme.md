**rss-feed.vm**

* Creates a simple RSS 2.0 feed with links to Page assets from an Index Block.
* Expects Cascade Server version 6.10+ so if you're using a version prior to that, switch the `$_EscapeTool.xml()` calls to a `$_SerializerTool.serialize()`.
