---
name: "Angular Materialメモ"
slug: "fgsxpum"
tags: ["Angular"]
---

# Angular Materialメモ

## Button

```typescript
import {MatButtonModule} from '@angular/material/button';
```

```xml
<button mat-button>Click me!</button>
```


## Button toggle

```typescript
import {MatButtonToggleModule} from '@angular/material/button-toggle';
```

```xml
<mat-button-toggle-group name="fontStyle" aria-label="Font Style">
  <mat-button-toggle value="bold">Bold</mat-button-toggle>
</mat-button-toggle-group>
```


## Checkbox

```typescript
import {MatCheckboxModule} from '@angular/material/checkbox';
```

```html
<mat-checkbox>Check me!</mat-checkbox>
```


## Icon

```typescript
import { MatIconModule } from '@angular/material/icon';
```

```html
<mat-icon aria-hidden="false" aria-label="Example home icon">
  home
</mat-icon>
```


## Slide toggle

```typescript
import {MatSlideToggleModule} from '@angular/material/slide-toggle';
```

```html
<mat-slide-toggle>
  Slide me!
</mat-slide-toggle>
```
