# Disable Speculative Loading

```
// Disable Speculative Loading

add_filter('wp_speculative_loading_enabled', '__return_false');
remove_action('wp_head', 'wp_output_speculationrules_script');

add_action('template_redirect', function () {
	ob_start(function ($html) {
			return preg_replace('/<script type="speculationrules">.*?<\/script>/s', '', $html);
	});
});
```

[Tutorial](https://youtu.be/mtyIzyplXR4)

[WebStylePress](https://www.youtube.com/@webstylepress)
