The combination of the Twitter Widget Data Definition and Velocity Format will provide a means of embedding Twitter Widgets onto Cascade Pages.

More information about Twitter Widgets (Embeddable Timelines) and the available options can be found [here][twitter-docs-embedded-timelines].

[twitter-widget-dd.xml](https://github.com/hannonhill/Velocity-Cookbook/blob/master/Twitter-Widget/twitter-widget-dd.xml)
========
* The Data Definition to be used for Twitter Widget Structured Data Blocks.

[twitter-widget.vm](https://github.com/hannonhill/Velocity-Cookbook/blob/master/Twitter-Widget/twitter-widget.vm)
========
* Creates a Twitter Widget based on Structured Data from the Data Definition above.

Prerequisite
========
A valid [Twitter Widget must be created][twitter-docs-embedded-timelines] through the desired Twitter account prior to embedding a widget.

Usage
========
1. Create a new Structured Data Block using the Twitter Widget Data Definition
2. Attach both the Structured Data Block and Velocity Format to a Template Region.

Fields/Options
========
* **Widget Embed Code:** (required) the embed code provided by Twitter after creating a [Twitter Widget][twitter-docs-embedded-timelines].
* **Dimensions**
    * **Width/Height:** specifies the fixed width and height (in pixels) of the widget. If left blank, the width of the widget will be fluid to its parent container on the page.
* **Widget Appearance**
    * **Tweet Limit:** Fix the size of a timeline to a preset number of Tweets (between 1 and 20). The timeline will render the specified number of Tweets from the timeline, expanding the height of the widget to display all Tweets without scrolling. Since the widget is of a fixed size, it will not poll for updates when using this option.
    * **Theme:** defaults to "light". Display the widget using a light or dark theme.
    * **Border Color:** defaults to #0088cc. Change the border color used by the widget.
    * **Border Color:** defaults to #c99826. Change the link color used by the widget.
    * **Remove Header:** Hides the timeline header. Please refer to the timeline [display requirements][twitter-docs-display-terms] when implementing your own header.
    * **Remove Footer:** Hides the timeline footer and Tweet box, if included.
    * **Remove Borders:** Removes all borders within the widget (between Tweets, cards, around the widget.)
    * **Remove Scrollbar:** Crops and hides the main timeline scrollbar, if visible. Please consider that hiding standard user interface components can affect the accessibility of your website.
    * **Make Transparent:** Removes the background color.
	* Note: All colors should be a valid Hex format (eg #000 or #000000)

[twitter-docs-embedded-timelines]: https://dev.twitter.com/docs/embedded-timelines
[twitter-docs-display-terms]: https://dev.twitter.com/terms/display-requirements
