# Laravel htaccess

```
# PHP7 for Locaweb
AddHandler php71-script .php
suPHP_ConfigPath /home/{your-domain}/

# Redirection rule from one domain to another
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %http://example.net/$ [OR]
    RewriteRule ^(.*)$ http://example.com [R=301,L]
</IfModule>

# Redirection rule for https domain
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %http://example.com/$ [OR]
    RewriteRule ^(.*)$ https://example.com/ [R=301,L]
</IfModule>

# Redirect rule to remove public from URL
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteRule ^$ public/ [L]
    RewriteRule (.*) public/$1 [L]
</IfModule>
```
