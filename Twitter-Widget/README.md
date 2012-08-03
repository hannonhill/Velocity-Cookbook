The combination of the Twitter Widget Data Definition and Velocity Format will provide a means of embedding Twitter Widgets onto Cascade Pages. 

More information about Twitter Widgets and the available options can be found [here](https://twitter.com/about/resources/widgets).

twitter-widget-dd.xml
========
* The Data Definition to be used for Twitter Widget Structured Data Blocks.

twitter-widget.vm
========
* Creates a Twitter Widget based on Structured Data from the Data Definition above.

Usage
========
1. Create a new Structured Data Block using the Twitter Widget Data Definition
2. Attach both the Structured Data Block and Velocity Format to a Template Region.

Available Widget Types
========
* **Profile:** Display your most recent Twitter updates on any webpage.
* **Search:** Displays search results based on search query.
* **Faves:** Displays your favorite tweets.

Fields/Options
========
* **Username:** required for Profile and Faves widgets. Enter the Twitter username you wish to display tweets for.
* **Query:** required for Search widget. Enter the the desired query to search Twitter.  Advanced search examples can be found [here](https://support.twitter.com/articles/71577).
* **Title/Caption:** applicable for Search and Faves widgets. Displays title and caption text in the header of the widget
* **Dimensions**
    * **Width/Height:** specifies the fixed width and height (in pixels) of the widget.
    * **Auto Width:** choosing this option will create a responsive widget that will be as wide as its container.
* **Preferences**
    * **Poll for new results:** defaults to false. Loads new tweets automatically.
    * **Include Scrollbar:** defaults to false. Provides a means to scroll through the tweets within the widget.
    * **Behavior:** defaults to Timed Interval. 
        * **Timed Interval:** displays tweets based on the Timed Interval and Loop fields.
        * **Load all tweets:** displays all tweets at once.
    * **Loop results:** applicable for Timed Interval Behavior; defaults to false. Loop through the resulting tweets.
    * **Tweet Interval:** applicable for Timed Interval Behavior; defaults to 30. Interval for displaying new tweets.
    * **Number of Tweets:** defaults to 4. Number of tweets to display within the widget.           
    * **Advanced preferences**
        * **Show hashtags:** defaults to true. Setting to false will hide hashtags.
        * **Show avatars:** defaults to false. Setting to true will show user avatars.
        * **Fullscreen mode:** defaults to false. Setting to true will give you a full viewport sized widget.
* **Appearance**
    * **Shell Background:** defaults to #0088cc. Background color of the widget's header and footer area.
    * **Shell Text:** defaults to #fff. Text color of the widget's header and footer area.
    * **Tweet Background:** defaults to #fff. Background color of the tweet area.        
    * **Tweet Text:** defaults to #333. Text color of the tweet area.
	* **Link Text:** defaults to #c99826. Text color of the links within the tweet area.    
	* Note: All colors should be valid Hex Values (eg #000 or #000000)