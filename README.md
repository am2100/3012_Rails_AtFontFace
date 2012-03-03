# Set up rails to serve font assets using @font-face.
These instructions and resources gleaned from various sources:

- The good folk at Font Squirrel http://www.fontsquirrel.com/
- Tim Brown, Web Font Specimen http://webfontspecimen.com/
- Jared Sartin, Atomic Spin http://spin.atomicobject.com/2011/09/26/serving-fonts-in-rails-3-1/
- Tjobbe Andrews, Milton Bayer http://www.miltonbayer.com/font-face

Thanks to you all!

Nb. Beyond the fact that this works for my Windows XP system, I can offer you no guarantees!

## Browse for fonts at [Font Squirrel](http://www.fontsquirrel.com/fontface)

View @ff Demo

Download & unzip @font-face Kit

Nb. All fonts must be legally eligible for web embedding. Check the EULA if you are unsure.

### Make a note of font-names
You'll need these for referencing fonts on the client - if they are installed.

View Font

The font names are in the drop down menu at the top left of the font sample.

## Process your chosen fonts through the [@font-face Kit Generator](http://fontsquirrel.com/fontface/generator)
See [The Official 'How to use the Generator' Post](http://www.fontsquirrel.com/forum/discussion/5/generator-the-official-how-to-use-the-generator-post#Item_1) for details.
Upload either .ttf / .otf / .pfb font files for processing.
Download your kit.

## Add fonts and stylesheet.css to your rails app
### Rename stylesheet
>\> ren [drive:][path]stylesheet.css fonts.css.scss.erb

### Add fonts and renamed stylesheet
to: vendor/assets/fonts

## Amend fonts.css.scss.erb
### Add rails asset_paths
src: url('opensans-light-webfont-webfont.eot');
=>
src: url('<%= asset_path('opensans-light-webfont-webfont.eot') %>');

### Add local src: to beginning of third line
src: url('<%= asset_path('opensans-light-webfont-webfont.eot?#iefix') %>') format('embedded-opentype'),
=>
src: local('Open Sans Light'), url('<%= asset_path('opensans-light-webfont-webfont.eot?#iefix') %>') format('embedded-opentype'),

>\> Command Line

    Code
