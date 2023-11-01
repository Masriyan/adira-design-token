# List group

List groups are a flexible and powerful component for displaying a series of content. Modify and extend them to support just about any content within.

```js script
import { html } from 'lit';
import '../../tokens/src/styles.css';
```

<br />

### Example

The most basic list group is an unordered list with list items and the proper classes. Build upon it with the options that follow, or with your own CSS as needed.

```html preview-story
<ul class="list-group">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
```

<br />

### Active Items

Add <code>.active</code> to a <code>.list-group-item</code> to indicate the current active selection.

```html preview-story
<ul class="list-group">
  <li class="list-group-item active">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
```

<br />

### Disabled Items

Add <code>.disabled</code> to a <code>.list-group-item</code> to make it appear disabled. Note that some elements with <code>.disabled</code> will also require custom JavaScript to fully disable their click events (e.g., links).

```html preview-story
<ul class="list-group">
  <li class="list-group-item disabled">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
```

<br />

### Links and Buttons

Use <code>&lt;a&gt;</code>s or <code>&lt;button&gt;</code>s to create actionable list group items with hover, disabled, and active states by adding .list-group-item-action. We separate these pseudo-classes to ensure list groups made of non-interactive elements (like <code>&lt;li&gt;</code>s or <code>&lt;div&gt;</code>s)don’t provide a click or tap affordance.

Be sure to **not use the standard <code>.btn</code> classes here.**

```html preview-story
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action active">
    Cras justo odio
  </a>
  <a href="#" class="list-group-item list-group-item-action"
    >Dapibus ac facilisis in</a
  >
  <a href="#" class="list-group-item list-group-item-action">Morbi leo risus</a>
  <a href="#" class="list-group-item list-group-item-action"
    >Porta ac consectetur ac</a
  >
  <a href="#" class="list-group-item list-group-item-action disabled"
    >Vestibulum at eros</a
  >
</div>
```

<br />

With <code>&lt;button&gt;</code>s, you can also make use of the disabled attribute instead of the .disabled class. Sadly, <code>&lt;a&gt;</code>s don’t support the disabled attribute.

```html preview-story
<div class="list-group">
  <button type="button" class="list-group-item list-group-item-action active">
    Cras justo odio
  </button>
  <button type="button" class="list-group-item list-group-item-action">
    Dapibus ac facilisis in
  </button>
  <button type="button" class="list-group-item list-group-item-action">
    Morbi leo risus
  </button>
  <button type="button" class="list-group-item list-group-item-action">
    Porta ac consectetur ac
  </button>
  <button type="button" class="list-group-item list-group-item-action" disabled>
    Vestibulum at eros
  </button>
</div>
```

<br />

### Flush

Add <code>.list-group-flush</code> to remove some borders and rounded corners to render list group items edge-to-edge in a parent container (e.g., cards).

```html preview-story
<ul class="list-group list-group-flush">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
```

<br />

<!-- ## Contextual Classes

Use contextual classes to style list items with a stateful background and color.

```html preview-story
<ul class="list-group">
  <li class="list-group-item">Dapibus ac facilisis in</li>

  <li class="list-group-item list-group-item-primary">
    This is a primary list group item
  </li>
  <li class="list-group-item list-group-item-secondary">
    This is a secondary list group item
  </li>
  <li class="list-group-item list-group-item-success">
    This is a success list group item
  </li>
  <li class="list-group-item list-group-item-danger">
    This is a danger list group item
  </li>
  <li class="list-group-item list-group-item-warning">
    This is a warning list group item
  </li>
  <li class="list-group-item list-group-item-info">
    This is a info list group item
  </li>
  <li class="list-group-item list-group-item-light">
    This is a light list group item
  </li>
  <li class="list-group-item list-group-item-dark">
    This is a dark list group item
  </li>
</ul>
```

<br />

Contextual classes also work with <code>.list-group-item-action</code>. Note the addition of the hover styles here not present in the previous example. Also supported is the <code>.active</code> state; apply it to indicate an active selection on a contextual list group item.

```html preview-story
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action"
    >Dapibus ac facilisis in</a
  >

  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-primary"
    >This is a primary list group item</a
  >
  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-secondary"
    >This is a secondary list group item</a
  >
  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-success"
    >This is a success list group item</a
  >
  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-danger"
    >This is a danger list group item</a
  >
  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-warning"
    >This is a warning list group item</a
  >
  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-info"
    >This is a info list group item</a
  >
  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-light"
    >This is a light list group item</a
  >
  <a
    href="#"
    class="list-group-item list-group-item-action list-group-item-dark"
    >This is a dark list group item</a
  >
</div>
```

<br /> -->

### With badge

Add badges to any list group item to show unread counts, activity, and more with the help of some utilities.

```html preview-story
<ul class="list-group">
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Cras justo odio
    <span class="badge badge-primary badge-pill">14</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Dapibus ac facilisis in
    <span class="badge badge-primary badge-pill">2</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Morbi leo risus
    <span class="badge badge-primary badge-pill">1</span>
  </li>
</ul>
```

<br />

### Custom Content

Add nearly any HTML within, even for linked list groups like the one below, with the help of flexbox utilities.

```html preview-story
<div class="list-group">
  <a
    href="#"
    class="list-group-item list-group-item-action flex-column align-items-start active"
  >
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small>3 days ago</small>
    </div>
    <p class="mb-1">
      Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget
      risus varius blandit.
    </p>
    <small>Donec id elit non mi porta.</small>
  </a>
  <a
    href="#"
    class="list-group-item list-group-item-action flex-column align-items-start"
  >
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small class="text-muted">3 days ago</small>
    </div>
    <p class="mb-1">
      Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget
      risus varius blandit.
    </p>
    <small class="text-muted">Donec id elit non mi porta.</small>
  </a>
  <a
    href="#"
    class="list-group-item list-group-item-action flex-column align-items-start"
  >
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small class="text-muted">3 days ago</small>
    </div>
    <p class="mb-1">
      Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget
      risus varius blandit.
    </p>
    <small class="text-muted">Donec id elit non mi porta.</small>
  </a>
</div>
```

<br />
