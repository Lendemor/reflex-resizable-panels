# resizable-panels

A Reflex custom component resizable-panels.

## Installation

```bash
pip install reflex-resizable-panels
```

## Usage

```python
from reflex import rx
from reflex_resizable_panels import resizable_panels as rzp

def index():
    return rx.box(
        rzp.group(
            rzp.panel("Header", default_size=20, min_size=20),
            rzp.handle(),
            rzp.panel(
                "Content",
                background_color=rx.color("gray", 10),
                default_size=80,
                min_size=20,
            ),
        ),
        width="100vw",
        height="100vh",
    )
```

## API

### PanelGroup
- `children`: List of `Panel` and `Handle` components.
- `auto_save_id`: `str` - ID to save the layout in LocalStorage.
- `direction`: `Literal["horizontal", "vertical"]` - Direction of the panels. Default is `horizontal`.
- `onLayout`: Called when group layout changes.

### Panel
- `children`: `Component` - Content of the panel.
- `default_size`: `int` - Default size of the panels.
- `min_size`: `int` - Minimum size of the panels. Default is `10`.
- `max_size`: `int` - Maximum size of the panels. Default is `100`.
- `collapsible`: `bool` - If `True`, panel can be collapsed by resizing below `min_size`.
- `collapsed_size`: The size of the panel when it is collapsed. Default is `0`.
- `order`: `int` - Order of the panel in the group. Required when using panels in `rx.cond`

Disclaimer:
> Resizable panels don't work when used inside `rx.container`. However, `rx.container` inside resizable panels do work.
