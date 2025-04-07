
# PrimeReact Chip Component

## Usage Examples

### Import
```ts
import { Chip } from 'primereact/chip';
```

### Basic
A basic chip with a text is created with the `label` property. When `removable` is added, a delete icon is displayed to remove a chip.

```tsx
import React from 'react';
import { Chip } from 'primereact/chip';

export default function BasicDemo() {
    return (
        <div className="card flex flex-wrap gap-2">
            <Chip label="Action" />
            <Chip label="Comedy" />
            <Chip label="Mystery" />
            <Chip label="Thriller" removable />
        </div>
    );
}
```

### Icon
A font icon next to the label can be displayed with the `icon` property.

```tsx
import React from 'react';
import { Chip } from 'primereact/chip';

export default function IconDemo() {
    return (
        <div className="card flex flex-wrap gap-2">
            <Chip label="Apple" icon="pi pi-apple" />
            <Chip label="Facebook" icon="pi pi-facebook" />
            <Chip label="Google" icon="pi pi-google" />
            <Chip label="Microsoft" icon="pi pi-microsoft" removable />
        </div>
    );
}
```

### Image
The `image` property is used to display an image like an avatar.

```tsx
import React from 'react';
import { Chip } from 'primereact/chip';

export default function ImageDemo() {
    return (
        <div className="card flex flex-wrap gap-2">
            <Chip label="Amy Elsner" image="https://primefaces.org/cdn/primereact/images/avatar/amyelsner.png" />
            <Chip label="Asiya Javayant" image="https://primefaces.org/cdn/primereact/images/avatar/asiyajavayant.png" />
            <Chip label="Onyama Limba" image="https://primefaces.org/cdn/primereact/images/avatar/onyamalimba.png" />
            <Chip label="Xuxue Feng" image="https://primefaces.org/cdn/primereact/images/avatar/xuxuefeng.png" removable />
        </div>
    );
}
```

### Template
The `template` property allows displaying custom content inside a chip.

```tsx
import React from 'react';
import { Chip } from 'primereact/chip';

export default function TemplateDemo() {
    const content = (
        <>
            <span className="bg-primary border-circle w-2rem h-2rem flex align-items-center justify-content-center">P</span>
            <span className="ml-2 font-medium">PRIME</span>
        </>
    );

    return (
        <div className="card">
            <Chip className="pl-0 pr-3" template={content} />
        </div>
    );
}
```

### Accessibility
(Refer to official documentation for accessibility best practices.)

---

## API Reference

### Props

| Name        | Type                                             | Default | Description                                                                 |
|-------------|--------------------------------------------------|---------|-----------------------------------------------------------------------------|
| children    | ReactNode                                        |         | Used to get the child elements of the component.                            |
| icon        | IconType<ChipProps>                              |         | Defines the icon to display.                                               |
| image       | string                                           |         | Defines the image to display.                                              |
| imageAlt    | string                                           |         | Specifies alternate text for image if not displayed.                       |
| label       | string                                           |         | Defines the text to display.                                               |
| pt          | ChipPassThroughOptions                           |         | Pass attributes to DOM elements inside component.                          |
| ptOptions   | PassThroughOptions                               |         | Configure passthrough options.                                             |
| removable   | boolean                                          | false   | Whether to display a remove icon.                                          |
| removeIcon  | IconType<ChipProps>                              |         | Icon of the remove element.                                                |
| template    | TemplateType<ChipProps>                          |         | Template of an item.                                                       |
| unstyled    | boolean                                          | false   | Removes component-related styles.                                          |

### Methods

- `getElement()`: Returns the container element.
- `getVisible()`: Returns current visibility state.
- `setVisible(visible: boolean)`: Sets chip visibility.

### Callbacks

- `onImageError(event)`: Triggered if image loading fails.
- `onRemove(event)`: Triggered when a chip is removed.

### Events

**ChipRemoveEvent**

| Name          | Type                                | Description          |
|---------------|-------------------------------------|----------------------|
| originalEvent | SyntheticEvent<Element, Event>      | Browser event        |
| value         | string                              | Removed item value   |

---

## Theming

### Styled Mode Class Names

| Class Name           | Element                           |
|----------------------|------------------------------------|
| `p-chip`             | Container element                  |
| `p-chip-image`       | Container element in image mode    |
| `p-chip-text`        | Text of the chip                   |
| `pi-chip-remove-icon`| Remove icon                        |
