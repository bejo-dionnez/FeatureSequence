##FeatureSequence

FeatureSequence is a plugin built for the genome browser _JBrowse_.

It provides the user with a quick interactive tool for viewing the sequences of various features.

FeatureSequence allows the user to:

* View upstream and downstream sequences

* Toggle the display of different types of subfeatures
  * Introns are automatically assumed from exon boundaries
  * Easily retrieve spliced CDS

* Highlight any type of subfeature in a randomly selected pastel color
  * Highlights are preserved if copied into a rich text editor (MS Word, LibreOffice Writer, etc.)

* Change case of any type of subfeature
  * Can be used to map intron/exon junctions
  * Simplify RealTime qPCR primer design!


##To use the FeatureSequence plugin:
```
#Clone this repository into your jbrowse/plugins/ directory
git clone https://github.com/tsaari88/FeatureSequence

##You must also add a way to call FeatureSequence
# For example, you want to add a right-click menu option to
# launch FeatureSequence on your favorite Example_Track.
# Do this by editing trackList.json as follows:
...
         "key" : "Example_Track",
         "label" : "Example_Track",
         "menuTemplate" : [
            {},
            {},
            {
               "content" : "function(track,feature){return track.browser.plugins.FeatureSequence.callFxn(track, feature); }",
               "label" : "View Feature Sequence",
               "action" : "contentDialog",
               "iconClass" : "dijitIconBookmark"
            }
...
```

Now in JBrowse, when right-clicking a feature on Example_Track, you will have the option to "View Feature Sequence."
This will open up a Feature Sequence Viewer pop-up dialog with interactive features for a customized sequence view.

##Additional Details

FeatureSequence Author: Travis Saari.

In creating the plugin, I borrowed a lot of concepts and code from a similar plugin called [SeqLighter, which can be found at this link](https://github.com/Arabidopsis-Information-Portal/SeqLighter).

I have added the hide/show and text-case-change functionalities, as well as completely re-worked the code to run asynchronously and to minimize dependencies. I believe that this plugin will provide some much-desired functionality to JBrowse.
