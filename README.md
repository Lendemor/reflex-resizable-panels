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

Disclaimer:
> Resizable panels don't work when used inside `rx.container`. However, `rx.container` inside resizable panels do work.
