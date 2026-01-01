## Converting Quotes to Images

This contains a Python script to convert the list of quotes into png images. Although the file appears as a CSV and opens as one, it looks really awful in excel as the commas in the quotes are preserved so it breaks them into columns. I recommend opening and editing it in an actual text editor like Visual Studio Code.

The format is quite simple if you want to add new quotes or edit existing ones

* 24h time|time reference|literary quote with time reference inside it|Book Title|Author

Written as an example
* 16:15|quarter past four|At a quarter past four he stumbled home drunk|Foo-Book Title|Bar-Author

## Using the script
This requires [Python](https://apps.microsoft.com/store/search/python) 3.6 or higher, and the [Pillow](https://pillow.readthedocs.io/en/latest/installation.html#basic-installation) imaging library (`pip3 install pillow`)[^1].

Run the script with `python3 quote_to_image.py`, from the same folder as the csv file and fonts.

If you prefer to generate images without the author and title in them, you can open quote_to_image.py in a text editor and change the line that says "include_metadata" to "False". These will be saved to /images/nometadata/ by default.

Fonts can also be changed in this manner, simply add a new truetype font to this folder and edit the name of the appropriate entry.

If you only want to generate x images (say, for testing how a font or a quote looks), you can pass a number as an argument to the script — `python3 quote_to_image.py 5` will only process the first 5 lines in the csv file (excluding the header).

## Credits

Thanks to [tjaap](https://www.instructables.com/Literary-Clock-Made-From-E-reader/) for creating the original version of this script in PHP.

[^1]: Python is preinstalled on virtually every Linux distribution and MacOS, in which case you only need to install Pillow.

## Darryl's Updates

* CSV is sourced from JohanneseNE/literature-clock.  This CSV is missing header, but has extra "safe" field to ide    ntify sfw/nsfw quotes. Quotes are in Unicode, and include <br>s, so made some adjustments for that. There are a fe    w quotes that are not parsing properly. Couldn't figure out problem.  I'll try to identify those separately.
* I was generating images for a Kindle Paperwhite 2 which has a higher resolution than earlier Kindles, so I had t    o adjust imgsize and various numbers for the quote to image conversion.
* I'm displaying the Kindle upside-down for easier charging, so have to flip images 180 degrees.
* Future enhancements: 
    * use file directly without having to add header
    * add flags to generate sfw, nsfw-only (ha) quotes, etc.
