
# Unreal Engine Marketplace to Epic Games Launcher Redirect

This project provides a simple HTML page hosted on GitHub Pages that redirects users to the Epic Games Launcher, specifically to a product page on the Unreal Engine Marketplace, based on a given slug parameter.

## How It Works

When the HTML page is loaded, it extracts the `slug` parameter from the URL's query string and constructs a URL to open the Epic Games Launcher with the specified product page. If no `slug` parameter is provided, it displays an error message.

## Usage

To use this tool, simply append the `slug` parameter to the URL hosted on GitHub Pages.

### Example

To redirect to a specific product on the Unreal Engine Marketplace, use the following URL format:

```
https://rilith.github.io/EpicGamesLauncherRedirect/?slug=your-product-slug
```

Replace `your-product-slug` with the desired product's slug.

### Example URL with https://www.unrealengine.com/marketplace/en-US/product/content-examples

If the slug for a product is `content-examples`, the URL would be:

```
https://rilith.github.io/EpicGamesLauncherRedirect/?slug=content-examples
```

When users visit this URL, they will be redirected to the specified product page in the Epic Games Launcher.

## Code Overview

```html
<!DOCTYPE html>
<html>
<head>
    <title>Redirecting to Epic Games Launcher...</title>
    <script type="text/javascript">
        function redirectToLauncher() {
            var params = new URLSearchParams(window.location.search);
            var slug = params.get('slug');
            if (slug) {
                var launcherUrl = 'com.epicgames.launcher://ue/marketplace/product/' + slug;
                window.location.href = launcherUrl;
            } else {
                document.getElementById('message').innerText = 'Invalid request: No slug provided';
            }
        }
    </script>
</head>
<body onload="redirectToLauncher()">
    <p id="message">Redirecting to Epic Games Launcher...</p>
</body>
</html>
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes or improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Happy coding!
