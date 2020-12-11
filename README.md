# CSS

Random CSS files that match [Organizr](https://github.com/causefx/Organizr/)

## Installation

### Orgarr - skin for Sonarr, Radarr, Lidarr (v3 only)
Requires a [subfilter](http://nginx.org/en/docs/http/ngx_http_sub_module.html) to use. All you have to do is include 
the following into your reverse proxy block for whichever *arr.
```nginx
proxy_set_header Accept-Encoding "";
sub_filter
'</head>'
'<link rel="stylesheet" type="text/css" href="https://halianelf.github.io/css/orgarr.css">
</head>';
sub_filter_once on;
```

### Upptime
Specify the custom stylesheet in your `.upptimerc.yml`
```yaml
status-website:
  links:
    - rel: stylesheet
      href: https://halianelf.github.io/css/upptime.css
```

### LibreNMS
Place the config in the custom css folder. For the docker container this is `/opt/librenms/html/css/custom` 
(path may vary for native installs) and set your `custom_config.php` to use it like so:
```php
<?php
$config['webui']['custom_css'][]        = "css/custom/librenms.css";
```