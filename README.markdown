# timeago: a jQuery plugin

[![NPM](https://img.shields.io/npm/v/timeago.svg)](https://www.npmjs.com/package/timeago)
[![Bower](https://img.shields.io/bower/v/jquery-timeago.svg)](http://bower.io/search/?q=jquery-timeago)

Timeago is a jQuery plugin that makes it easy to support automatically updating
fuzzy timestamps (e.g. "4 minutes ago" or "about 1 day ago") from ISO 8601
formatted dates and times embedded in your HTML (à la microformats).

I have just disable units bigger than days.

## Usage

First, load jQuery and the plugin:

```html
<script src="jquery.min.js" type="text/javascript"></script>
<script src="jquery.timeago.js" type="text/javascript"></script>
```

Now, let's attach it to your timestamps on DOM ready - put this in the head
section:

```html
<script type="text/javascript">
   jQuery(document).ready(function() {
     $("time.timeago").timeago();
   });
</script>
```

This will turn all `<time>` elements with a class of `timeago` and a
`datetime` attribute formatted according to the
[ISO 8601](http://en.wikipedia.org/wiki/ISO_8601) standard:

```html
<time class="timeago" datetime="2011-12-17T09:24:17Z">December 17, 2011</time>
```

into something like this:

```html
<time class="timeago" datetime="2011-12-17T09:24:17Z" title="December 17, 2011">about 1 day ago</time>
```

`<abbr>` elements (or any other HTML elements) are also supported (this is for
[legacy microformat support](http://microformats.org/wiki/datetime-design-pattern)
and was originally supported by the library before the `time` element was
introduced to HTML5):

```html
<abbr class="timeago" title="2011-12-17T09:24:17Z">December 17, 2011</abbr>
```

As time passes, the timestamps will automatically update.

If you want to update a timestamp programatically later, call the `update`
function with a new ISO8601 timestamp of `Date` object. For example:

```javascript
$("time#some_id").timeago("update", "2013-12-17T09:24:17Z");
// or
$("time#some_id").timeago("update", new Date());
```

**For more usage and examples**: [http://timeago.yarp.com/](http://timeago.yarp.com/)

**For different language configurations**: visit the [`locales`](https://github.com/rmm5t/jquery-timeago/tree/master/locales) directory.

## Settings

**`cutoff`** : Return the original date if time distance is older than `cutoff` (miliseconds).

```javascript
// Display original dates older than 24 hours
jQuery.timeago.settings.cutoff = 1000*60*60*24;
```

## Changes

| Version | Notes                                                                           |
|---------|---------------------------------------------------------------------------------|
|   1.6.x | ([compare][compare-1.6]) Wraped locales in UMD wrappers; locale improvements    |
|   1.5.x | ([compare][compare-1.5]) Added Date as argument to update function; locales     |
|   1.4.x | ([compare][compare-1.4]) Added allowPast setting; locale updates                |
|   1.3.x | ([compare][compare-1.3]) Added updateFromDOM function; bug fixes; bower support |
|   1.2.x | ([compare][compare-1.2]) Added cutoff setting; locale updates                   |
|   1.1.x | ([compare][compare-1.1]) Added update function; locale updates                  |
|   1.0.x | ([compare][compare-1.0]) locale updates; bug fixes; AMD wrapper                 |
|  0.11.x | ([compare][compare-0.11]) natural rounding; locale updates;                     |
|  0.10.x | ([compare][compare-0.10]) locale updates                                        |
|   0.9.x | ([compare][compare-0.9]) microsecond support; bug fixes                         |
|   0.8.x | ([compare][compare-0.8]) `<time>` element support; bug fixes                    |
|   0.7.x | ([compare][compare-0.7]) locale function overrides; unit tests                  |
|     ... | ...                                                                             |

[compare-1.6]: https://github.com/rmm5t/jquery-timeago/compare/v1.5.4...v1.6.7
[compare-1.5]: https://github.com/rmm5t/jquery-timeago/compare/v1.4.3...v1.5.4
[compare-1.4]: https://github.com/rmm5t/jquery-timeago/compare/v1.3.2...v1.4.3
[compare-1.3]: https://github.com/rmm5t/jquery-timeago/compare/v1.2.0...v1.3.2
[compare-1.2]: https://github.com/rmm5t/jquery-timeago/compare/v1.1.0...v1.2.0
[compare-1.1]: https://github.com/rmm5t/jquery-timeago/compare/v1.0.2...v1.1.0
[compare-1.0]: https://github.com/rmm5t/jquery-timeago/compare/v0.11.4...v1.0.2
[compare-0.11]: https://github.com/rmm5t/jquery-timeago/compare/v0.10.1...v0.11.4
[compare-0.10]: https://github.com/rmm5t/jquery-timeago/compare/v0.9.3...v0.10.1
[compare-0.9]: https://github.com/rmm5t/jquery-timeago/compare/v0.8.2...v0.9.3
[compare-0.8]: https://github.com/rmm5t/jquery-timeago/compare/v0.7.2...v0.8.2
[compare-0.7]: https://github.com/rmm5t/jquery-timeago/compare/v0.6.2...v0.7.2

## Author

[Ryan McGeary](http://ryan.mcgeary.org) ([@rmm5t](http://twitter.com/rmm5t))

## License

[MIT License](https://rmm5t.mit-license.org/)
