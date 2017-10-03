Install:
* run `bundle install --binstubs --path=vendor` to install the required dependencies.
* run `brew install graphicsmagick`

If I get the issue:

conversion error: Jekyll::Converters::Scss encountered an error while converting 'css/pixyll.scss':
Invalid US-ASCII character "\xC2" on line 7
                    
I can do this: https://github.com/johnotander/pixyll/issues/193:
run this in the terminal

```
if locale -a | grep -qF 'C.UTF-8'; then
    loc="C.UTF-8"
else
    loc="en_US.UTF-8"
fi
export LANG=$loc
export LC_ALL=$loc
```

Comment out optimize images while developing, otherwise it is too slow to work.
Comment in _config.yml the lines

```
#mini_magick:

##Create Thumbs for the Archive Page
#    thumbnail:
#      source: images/comics/
#      destination: /images/comics/thumbs
#      resize: "182x280^"
#
##Autogenerate smaller size for small screens
#    small:
#      source: images/comics/
#      destination: /images/comics/small
#      resize: "350x535^"
```

run with:

`bundle exec jekyll serve --baseurl '' --watch`

## Build
install the html_compressor
`gem install html_compressor`

then run build:
`rake build`
