# Fullstory - Browser Tag

This repository is used for the [Fullstory - Browser Tag](https://tagmanager.google.com/gallery/#/owners/fullstorydev/templates/fullstory-gtm-template) in the Google GTM Community Template Gallery.

Automatically collect behavioral data into the Fullstory platform with the Fullstory Tag template.

# Fullstory

To find more information about Fullstory, please visit https://www.fullstory.com/

# GTM Tag Fields

### Org Id

The Fullstory Org Id must be provided. For more information on how to find the Org Id, visit the [help page here](https://help.fullstory.com/hc/en-us/articles/360047075853-How-do-I-find-my-Fullstory-Org-Id).

### Debug mode

Enable debug mode for Fullstory. This is useful for troubleshooting any issues with the Fullstory installation. For more information on debug mode, visit the [help page here](https://help.fullstory.com/hc/en-us/articles/360020829233-How-to-enable-debug-mode-for-Fullstory).

### Enable capture inside an iframe

Allow Fullstory to capture data from within an iframe. This is required only for certain implementation scenarios. This flag is equivalent to setting the global flag `window['_fs_run_in_iframe']`.

For more information about this flag please visit the [help page here](https://help.fullstory.com/hc/en-us/articles/360020622514-Can-Fullstory-capture-content-that-is-presented-in-iframes).

### Capture only this iframe

Makes the iframe the "root" of its own recording, as its own session. Use this when your page is embedded in an iframe on a site that does not run Fullstory, or when you want its content sent to a different Fullstory org. This flag is equivalent to setting the global flag `window['_fs_is_outer_script']`.

### Cookie Domain (Optional)

Overrides the domain the Fullstory cookie is valid for. By default the cookie is valid for all subdomains of your site; enter a domain such as `app.example.com` to limit it to a specific subdomain. Leave blank to use the default. This is equivalent to setting `window['_fs_cookie_domain']`.

For more information, visit the [help page here](https://help.fullstory.com/hc/en-us/articles/360020622874-Can-the-Fullstory-cookie-be-associated-with-a-specific-subdomain).

### Asset Map ID (Optional)

Sets the current asset map ID. Only needed if you upload assets to Fullstory. This is equivalent to setting `window['_fs_asset_map_id']`.

For more information, visit the [help page here](https://help.fullstory.com/hc/en-us/articles/4404129191575-Asset-Uploading-for-Web).

### Custom Endpoint (Optional)

If your org sends traffic through a Fullstory-managed Custom Endpoint (your own domain, CNAME'd to Fullstory), enter that domain here, e.g. `analytics.example.com`. Leave blank to use Fullstory's default domain.

For more information on Custom Endpoints, visit the [help page here](https://help.fullstory.com/hc/en-us/articles/18612999473175-How-to-send-captured-traffic-to-Fullstory-using-Custom-Endpoints).

# Delaying capture

This template does not have a "start capture manually" option. Starting capture later means calling `FS('start')`, and a template can only do that by being allowed to call any Fullstory API function, which is broader than this template's permissions. To delay capture, use Custom HTML tags instead:

1. Set `window['_fs_capture_on_startup'] = false;` in a Custom HTML tag that fires before this tag, for example on the Consent Initialization trigger.
2. Call `FS('start');` from another Custom HTML tag when you want capture to begin, for example when a user grants consent.

For more information, visit the [help page here](https://developer.fullstory.com/browser/v2/auto-capture/capture-data/#manually-delay-data-capture).
