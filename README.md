# Flexify

FlexSlider, a powerful and responsive image slider, for use in any Shopify theme.

Currently Flexify supports up to 5 images, with optional linking.

## Requirements

- jQuery 1.6.2 or higher

# Setup

Follow below to setup Flexify on your Shopify site.

### Asset uploads

Upload all the files from the assets folder into your theme assets.

### Snippet creation

Create a new snippet and name it '**flexify**'. Copy and paste the contents of **flexify.liquid** into the file and save.

### Settings

Add the contents of **settings.html** to the bottom of your theme's _Configs > settings.html_.

### Implement

Open your theme's _Layout > theme.liquid_, and add the following into your header.

```liquid
{% comment %}
	Load Flexify dependencies. Change template accordingly to enable the slider on other pages. Replace jquery.flexify.js with jquery.flexify.min.js for minified version. 
{% endcomment %}
{% if template == "index" and settings.slider_enabled %}
  {{ 'flexify.css' | asset_url | stylesheet_tag }}
  {{ 'jquery.flexify.js' | asset_url | script_tag }}
  <script type="text/javascript" charset="utf-8">
    $(window).load(function() {
      $('.flexify').flexify();
    });
  </script>
{% endif %}
```

Finally, include the Flexify snippet in your theme by adding the following in _Layout>theme.liquid_ wherever your heart desires. Don't forget to wrap it if necessary (_insert condom joke here_).

```liquid
{% if template == "index" and settings.slider_enabled %}
	{% include 'flexify' %}
{% endif %}
```

### Enjoy!

Upload images, add links, and edit slider settings directly from your theme settings. Enjoy your new slider!

###	Authors

- The awesome people who made [FlexSlider](https://github.com/woothemes/FlexSlider)
- Shopified by [Adrian Pawliszko](http://nairda.ca)