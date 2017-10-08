To generate several sizes for the banner, first install
* `npm install -g grunt-cli`

Install:
If in intellij exclude _site directory from the searches, it makes the search messy. Like so: https://stackoverflow.com/a/29014849/3094399

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
Just comment out the code int the .rb files in the _plugins folder. I should not need to do this,
given there is a caching mechanism, but it does not seem to work.

run with:

`rake watch` or `bundle exec jekyll serve --baseurl '' --watch`

## Build
install the html_compressor
`gem install html_compressor`

then run build:
`rake build`

## Social media
I followed this tutorial for adding social media links https://superdevresources.com/share-buttons-jekyll/
there I have examples for adding even more like linkeding.

## TODO
add reddit share link: https://icomoon.io/app/#/select
