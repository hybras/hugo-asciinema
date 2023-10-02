# Hugo Asciinema

This incomplete theme contributes a shortcode and partial to be used with other themes to embed asciicasts into your site. The asciicast file itself may be anywhere, not just locally. The css and js assets come from the player's [latest release](https://github.com/asciinema/asciinema-player/releases/latest). At the time of writing, that was [v2.6.1](https://github.com/asciinema/asciinema-player/releases/tag/v2.6.1).

## Usage

Add the following to your `hugo.yaml`.

```yaml
module:
  imports:
    - path: 'github.com/hybras/hugo-asciinema'
```

### Shortcode

1 Positional parameter, the url to the cast file

```html
{{< asciicast hello_world.cast >}}
```

All Named parameters. All [player attributes are supported](https://github.com/asciinema/asciinema-player/tree/master#asciinema-player-element-attributes).

```html
{{< asciicast src="hello_world.cast" speed="1.2" >}}
```

### Partial

Include this somehow in `<head>`. Hugo themes can have their layouts overriden. You can override your theme's header. My theme has a special sections to be overriden, so users can append content to `<head>` without overwriting it.

{{ partial "asciinema.html" . }}
