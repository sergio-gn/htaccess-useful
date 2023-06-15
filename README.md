# Useful pieces of code that for helping fast implementation of htaccess rules

## Direct Redirect inside the same website:
RedirectMatch 301 /slug/the-redirected-page/ https://yourwebsite.com.au/new-page/

## Redirect every page with '?' after the domain. Exclude the homepage
RewriteEngine On <br>
RewriteCond %{QUERY_STRING} . <br>
RewriteRule ^$ /404/? [R=301,L] <br>

## Redirect as many url as you want with the same pattern to a new slug
Example:  <br>
https://example.com.au/example-removethispart-page-sydney/ <br>
https://example.com.au/example-removethispart-page-melbourne/ <br>

RewriteEngine On <br>
RewriteRule ^example-removethispart-page-(.*)$ /example-page-$1 [R=301,L]
