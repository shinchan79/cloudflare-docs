---
_build:
	publishResources: false
	render: never
	list: never

name: "Enable `cache: no-store` HTTP standard API"
sort_date: "2024-11-11"
enabled_date: "2024-11-11"
enable_flag: "cache_option_enabled"
disable_flag: "cache_option_disabled"
---

When this flag is enabled, the cache header becomes available within the [`fetch()` API](/workers/runtime-apis/fetch/). The option for `no-store` is enabled.

For a cross-zone request this simply specifies the headers `Pragma: no-cache` and `Cache-Control: no-cache` to the origin.

For grey-cloud subrequests this bypasses the Cloudflare's cache.

Example:

```js
const response = await fetch("https://example.com", { cache: 'no-store'});
```