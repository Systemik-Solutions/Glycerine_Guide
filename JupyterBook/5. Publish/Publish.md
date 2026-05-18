# Publish

There are two steps to publishing in the Image Annotation Workbench. First, publish the Image Set. Then, publish individual Annotation Sets so they can be seen on the public Image Set.

## 1. Publish an Image Set

You can only publish Image Sets that you have created yourself.

1.	Click the three dots next to the Image Set you want to publish.
2.	Click **Publish**.
3.	Press **Yes** in the popup if you want to proceed.

Your Image Set can now be shared with others via the **Public URL**. To find this, press the three dots again and press **Public URL**.

You can also press **Unpublish** at any time.

## 2. Publish Annotation Sets

You can only publish Annotation Sets that you have created yourself.

1.	Click the three dots next to the Image Set you want to publish annotations for.
2.	Click **Annotate**.
3.	Next to the Annotation Set you want to publish, press the **Publish** button.
4.	Press **Yes** in the popup if you want to proceed.

Your Annotation Set can now be seen on the Image Set via the **Public URL**.

> Once you've published your annotation set you can also press the **Share** icon next to the set to find the IIIF Annotation Collection Manifest, which contains the annotation data only. You can reference this in a digital asset or collections management system to aggregate annotation sets with existing manifests.

## 3. URL parameters for Image Set publications

The published Image Set viewer accepts URL parameters that configure its initial state. Append them to the **Public URL** as a standard query string, for example:

```
https://iaw.ardc-hdcl-sia-iaw.cloud.edu.au/publications/image-sets/01hm598yb6hc3s7btmqth813mg?infopanel=0&autoplay=1&light=70
```

This is useful when embedding the viewer in another site, sharing a link that opens on a specific canvas or annotation, or pre-filtering annotations by collection, language, colour, or weight.

These parameters only set the **initial** state of the viewer when the publication is opened. Most of them can still be overridden by the user afterwards through the viewer's own controls (settings pane, filters, playback controls, etc.).

### Show / hide interface elements

These accept `1` (show) or `0` (hide). When omitted, the viewer default is used.

| Parameter | Controls |
| --- | --- |
| `infopanel` | The info panel beside the image. |
| `fullscreenbutton` | The full-screen button. |
| `indexbutton` | The index (canvas list) button. |
| `annotationviewbutton` | The annotation view button. |
| `aboutpanebutton` | The about button. |
| `settingpanebutton` | The settings button. |
| `playcontrols` | The annotation play controls. |

### Starting position

| Parameter | Value | Description |
| --- | --- | --- |
| `start_canvas` | URL-encoded canvas `id` | The canvas to display when the viewer opens. Overrides the manifest's own `start` property. Ignored if the id is not in the manifest. |
| `start_annotation` | URL-encoded annotation `id` | The annotation to focus initially. The viewer opens that annotation's canvas and pans/zooms to it. Takes priority over `start_canvas`. Ignored if the id is not found or if the active annotation filters would exclude it. |

### Annotation filters

These set the viewer's initial annotation filter selections. Annotations that don't match are hidden until the user clears the filter.

| Parameter | Value | Description |
| --- | --- | --- |
| `default_annotation_set` | URL-encoded annotation collection `id` | Show only annotations in this collection. |
| `default_annotation_language` | Language code, e.g. `en`, `fr` | Show only annotations in this language. |
| `default_line_color` | `blue`, `green`, `red`, `yellow`, `purple`, `orange`, `pink`, `brown`, `gray` | Show only annotations drawn in this colour. |
| `default_line_weight` | `light`, `medium`, `dark` | Show only annotations drawn with this line weight. |

### Annotation display

| Parameter | Value | Description |
| --- | --- | --- |
| `fill_opacity` | Number between `0` and `1` (one decimal place, e.g. `0.3`) | Fill opacity for annotation shapes. |
| `cutout` | `0` or `1` | Whether to display the annotation cutout by default. |
| `popup_position` | `top`, `bottom`, `left`, `right`, `topleft`, `topright`, `bottomleft`, `bottomright`, `center` | Position of the annotation popup relative to the annotation. |

### Playback

| Parameter | Value | Description |
| --- | --- | --- |
| `autoplay` | `0` or `1` | Automatically start playing annotations after the manifest loads. |
| `play_speed` | `3000` (fast), `5000` (normal), or `10000` (slow) | Time in milliseconds spent on each annotation during playback. |
| `play_popup` | `0` or `1` | Whether to show the annotation popup while playing. |

### Image

| Parameter | Value | Description |
| --- | --- | --- |
| `light` | Integer between `0` and `100` | The image light (brightness) level. |
