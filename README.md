# Phoenix LiveView Lucide Icons

A collection of Phoenix LiveView Components for all SVG [Lucide Icons](https://lucide.dev/). Lucide Icons is a community fork of Feather Icons.

Based on [Phoenix LiveView Heroicons](https://github.com/rocketinsights/heroicons_liveview).

## Installation

```elixir
def deps do
  [
    {:lucide_live_view, "~> 0.1.0"}
  ]
end
```

## Usage

### Basic usage

```html
<Lucide.activity />
```

### Dynamic Rendering:

Use the `render` function to dynamically select an icon based on a variable:

```html
<Lucide.render icon="activity" />
```

### Passing Additional Attributes

Besides, any attributes passed in will be forwarded to the svg element.

```html
<Lucide.activity
  id="my-activity-icon"
  class="inline-block h-5 w-5"
  stroke_width="1.5"
/>
```

## Creating Your Own Component

For further customization, consider wrapping Lucide icons within your own components.

```elixir
# core_components.ex

attr :name, :string, required: true
attr :class, :string, required: false, default: "icon"
attr :rest, :global

def icon(assigns) do
  ~H"""
  <Lucide.render icon={@name} class={@class} {@rest} />
  """
end
```

This approach allows you to define and use custom attributes for your icon components.

### Usage in .html.heex Files

Use your custom component in your HTML (html.heex) files:

```html
<.icon name="circle" />
```

## Regenerate icons

Update the Lucide Git submodule to a specific version:

```bash
mix lucide.update 1.7.0
```

Generate icons:

```bash
mix lucide.gen
```

## License

Source code is licensed under the [MIT License](LICENSE.md).
