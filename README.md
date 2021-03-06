#Hulu PHP Library
*A PHP Class*

##Description
**Author**: Adam Magaña &lt;holla@adammagana.com&gt;  
**Last Edit**: Oct 1st, 2012  
**Version**: 0.0.1

This PHP class provides simple methods for retrieving Hulu content. Hulu does not have an official API. However, this class exposes some of Hulu's hidden API-esque endpoints. Enjoy it while it lasts!

##Usage

**Constructor**
```php
$hulu = new Hulu();
```

All request methods have a `total` option. If this is set to `true` then the response will return only the total items generated by the request.

*Note: All Hulu responses are in XML format, so we return SimpleXML objects*

**Retrieving A Listing of Companies**
```php
$options = array(
    "limit" => "10",
    "order_by" => "name%20asc",
    "page" => "1",
    "total" => "0"
);
$companies = $hulu->getCompanies($options);
```

**Retrieving A Genre Listing**
```php
$options = array(
    "limit" => "10",
    "order_by" => "name%20asc",
    "page" => "1",
    "total" => "0"
);
$genres = $hulu->getGenres($options);
```

**Retrieving A Show Listing**
```php
$options = array(
    "limit" => "10",
    "order_by" => "name%20asc",
    "page" => "1",
    "total" => "0"
);
$shows = $hulu->getShows($options);
```
You can can also pass `company_id` parameter in options to filter shows by company. A `channel` parameter can be used to filter by **genre** as well. This is an odd language piece that Hulu uses. Not my choice!

**Retrieving A Video Listing**
```php
$options = array(
    "limit" => "10",
    "order_by" => "name%20asc",
    "page" => "1",
    "total" => "0"
);
$videos = $hulu->getVideos($options);
```
Passing a `show_id` parameter in options will filter videos by show.

**Searching**
```php
$results = $hulu->search("Beavis and Butthead", 10, 1);
```
The first parameter is the query string, the second is the result limit and the third is result page requested.

##License

(The MIT License)

Copyright (c) 2012 Adam Magaña &lt;holla@adammagana.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.