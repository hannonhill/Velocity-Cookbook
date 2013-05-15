**basic-rss-feed.vm**

* Creates a simple RSS 2.0 feed with links to Page assets from an Index Block.
* Uses the Calling Page data to populate the feed's Title and Link elements.
* Expects Cascade Server version 6.10+ so if you're using a version prior to that, switch the `$_EscapeTool.xml()` call to a `$_SerializerTool.serialize()` call.
