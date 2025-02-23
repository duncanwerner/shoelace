# Drawer

[component-header:sl-drawer]

Drawers slide in from a container to expose additional options and information.

```html preview
<sl-drawer label="Drawer" class="drawer-overview">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  <sl-button slot="footer" type="primary">Close</sl-button>
</sl-drawer>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-overview');
    const openButton = drawer.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());
  })();
</script>
```

## Examples

### Slide in From Left

To make the drawer slide in from the left, set the `placement` attribute to `left`.

```html preview
<sl-drawer label="Drawer" placement="left" class="drawer-placement-left">
  This drawer slides in from the left.
  <sl-button slot="footer" type="primary">Close</sl-button>
</sl-drawer>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-placement-left');
    const openButton = drawer.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());
  })();
</script>
```

### Slide in From Top

To make the drawer slide in from the top, set the `placement` attribute to `top`.

```html preview
<sl-drawer label="Drawer" placement="top" class="drawer-placement-top">
  This drawer slides in from the top.
  <sl-button slot="footer" type="primary">Close</sl-button>
</sl-drawer>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-placement-top');
    const openButton = drawer.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());
  })();
</script>
```

### Slide in From Bottom

To make the drawer slide in from the bottom, set the `placement` attribute to `bottom`.

```html preview
<sl-drawer label="Drawer" placement="bottom" class="drawer-placement-bottom">
  This drawer slides in from the bottom.
  <sl-button slot="footer" type="primary">Close</sl-button>
</sl-drawer>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-placement-bottom');
    const openButton = drawer.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());
  })();
</script>
```

### Contained to an Element

By default, the drawer slides out of its [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block#Identifying_the_containing_block), which is usually the viewport. To make the drawer slide out of its parent element, add the `contained` prop and `position: relative` to the parent.

```html preview
<div
  style="position: relative; border: solid 2px var(--sl-panel-border-color); height: 300px; padding: 1rem; margin-bottom: 1rem;"
>
  The drawer will be contained to this box. This content won't shift or be affected in any way when the drawer opens.

  <sl-drawer label="Drawer" contained class="drawer-contained" style="--size: 50%;">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    <sl-button slot="footer" type="primary">Close</sl-button>
  </sl-drawer>
</div>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-contained');
    const openButton = drawer.parentElement.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());
  })();
</script>
```

### Custom Size

Use the `--size` custom property to set the drawer's size. This will be applied to the drawer's width or height depending on its `placement`.

```html preview
<sl-drawer label="Drawer" class="drawer-custom-size" style="--size: 50vw;">
  This drawer is always 50% of the viewport.
  <sl-button slot="footer" type="primary">Close</sl-button>
</sl-drawer>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-custom-size');
    const openButton = drawer.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());
  })();
</script>
```

### Scrolling

By design, a drawer's height will never exceed 100% of its container. As such, drawers will not scroll with the page to ensure the header and footer are always accessible to the user.

```html preview
<sl-drawer label="Drawer" class="drawer-scrolling">
  <div style="height: 150vh; border: dashed 2px var(--sl-color-gray-80); padding: 0 1rem;">
    <p>Scroll down and give it a try! 👇</p>
  </div>
  <sl-button slot="footer" type="primary">Close</sl-button>
</sl-drawer>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-scrolling');
    const openButton = drawer.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());
  })();
</script>
```

### Ignoring Clicks on the Overlay

By default, drawers are closed when the user clicks or taps on the overlay. To prevent this behavior, cancel the `sl-overlay-dismiss` event.

```html preview
<sl-drawer label="Drawer" class="drawer-no-overlay-dismiss">
  This drawer will not be closed when you click outside of it.
  <sl-button slot="footer" type="primary">Close</sl-button>
</sl-drawer>

<sl-button>Open Drawer</sl-button>

<script>
  (() => {
    const drawer = document.querySelector('.drawer-no-overlay-dismiss');
    const openButton = drawer.nextElementSibling;
    const closeButton = drawer.querySelector('sl-button[type="primary"]');

    openButton.addEventListener('click', () => drawer.show());
    closeButton.addEventListener('click', () => drawer.hide());

    drawer.addEventListener('sl-overlay-dismiss', event => event.preventDefault());
  })();
</script>
```

[component-metadata:sl-drawer]
