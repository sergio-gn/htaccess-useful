# Useful pieces of code that for helping fast implementation of htaccess rules

## Direct Redirect inside the same website:
RedirectMatch 301 /slug/the-redirected-page/ https://yourwebsite.com.au/new-page/

## Redirect every page with '?' after the domain. Exclude the homepage
RewriteEngine On
RewriteCond %{QUERY_STRING} .
RewriteRule ^$ /404/? [R=301,L]
