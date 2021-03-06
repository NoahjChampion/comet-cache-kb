---
title: How do I customize IP address detection?
categories: questions
tags: themeplugin-developers
author: raamdev
github-issue: https://github.com/websharks/comet-cache-kb/issues/51
toc-enable: off
---

When detecting the remote IP address, Comet Cache uses the following lookup order, where each source is an array key in the [`$_SERVER` superglobal](http://php.net/manual/en/reserved.variables.server.php). We use the first public IPv4 or IPv6 address found in these headers, starting from the top and working down.

```text
'HTTP_CF_CONNECTING_IP',
'HTTP_CLIENT_IP',
'HTTP_X_FORWARDED_FOR',
'HTTP_X_FORWARDED',
'HTTP_X_CLUSTER_CLIENT_IP',
'HTTP_FORWARDED_FOR',
'HTTP_FORWARDED',
'HTTP_VIA',
'REMOTE_ADDR',
```

To modify the list of sources, you can create an [Advanced Cache Plugin](https://github.com/websharks/comet-cache-kb/issues/5); create this directory and file:
`/wp-content/ac-plugins/zc-ip-sources.php`

```php
<?php
$ac = $GLOBALS['comet_cache__advanced_cache'];
$ac->add_filter('comet_cache\\share::current_ip_sources', function($sources)
{
    // A source is an array key in the `$_SERVER` superglobal.
    return array(
     'HTTP_CF_CONNECTING_IP',
     'HTTP_CLIENT_IP',
     'HTTP_X_FORWARDED_FOR',
     'HTTP_X_FORWARDED',
     'HTTP_X_CLUSTER_CLIENT_IP',
     'HTTP_FORWARDED_FOR',
     'HTTP_FORWARDED',
     'HTTP_VIA',
     'REMOTE_ADDR',
    );
});
```

### Forcing the Old Behavior

Older versions of Comet Cache used only `$_SERVER['REMOTE_ADDR']`. If you want to revert to this old behavior, you can create an [Advanced Cache Plugin](https://github.com/websharks/comet-cache-kb/issues/5); create this directory and file:
`/wp-content/ac-plugins/zc-ip-source-remote-addr-only.php`

```php
<?php
$ac = $GLOBALS['comet_cache__advanced_cache'];
$ac->add_filter('comet_cache\\share::current_ip_prioritize_remote_addr', function(){ return true; });
```

With this filter in place, if `$_SERVER['REMOTE_ADDR']` is set and it's a public IP, we will use that without checking anything else; i.e., attempting to replicate the old behavior.

However, if `$_SERVER['REMOTE_ADDR']` is empty, or it's not a public IP, we will still skip it and continue searching through the new list of sources.
