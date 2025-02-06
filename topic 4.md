# SVG Graphics

## Scalable Vector Graphics (SVG)

### Definition
SVG stands for **Scalable Vector Graphics**. It’s a vector-based image format defined using XML. Unlike raster images (PNG, JPG), SVG images retain their quality regardless of size.

### Features
- **Resolution-independent**: Can scale up or down without pixelation.
- **Editable**: Can be modified with a text editor or tools like Adobe Illustrator or Inkscape.
- **Lightweight**: Efficient and suitable for web use.
- **Interactive**: Supports JavaScript and CSS for animations and interactivity.

### Why Use SVG?
- Ideal for **logos, icons, charts, and illustrations**.
- Can be directly embedded into HTML using `<svg>` tags.

#### Example: Simple SVG Circle
```xml
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
```

## Vector Graphics

### Definition
Vector graphics are made of paths defined by mathematical equations rather than pixels.

### Key Characteristics
- **Scalability**: Always sharp and clear, no matter the size.
- **Lightweight**: Stores data about shapes rather than individual pixels.

### Comparison
| Format  | Type         | Quality on Resize |
|---------|-------------|-------------------|
| Raster  | Pixel-based | Decreases        |
| Vector  | Path-based  | Constant         |

## Shapes in SVG
SVG allows creating various geometric shapes using predefined tags.

### Examples
#### Rectangle
```xml
<svg width="200" height="100">
  <rect width="200" height="100" style="fill:blue;stroke:black;stroke-width:2;" />
</svg>
```
#### Circle
```xml
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" fill="yellow" />
</svg>
```
#### Line
```xml
<svg width="200" height="100">
  <line x1="0" y1="0" x2="200" y2="100" style="stroke:black;stroke-width:2" />
</svg>
```
#### Polygon
```xml
<svg width="200" height="200">
  <polygon points="50,10 90,80 10,80" style="fill:lime;stroke:purple;stroke-width:1" />
</svg>
```

## Text in SVG
SVG supports text rendering using the `<text>` element.

### Attributes
- **x, y**: Position coordinates.
- **font-family, font-size**: Styling properties.

#### Example
```xml
<svg width="200" height="100">
  <text x="10" y="40" font-family="Arial" font-size="24" fill="black">
    Hello, SVG!
  </text>
</svg>
```

## Effects and Filters
SVG provides powerful filters for applying effects like blur, shadow, and color manipulation.

### Common Filters
- **Gaussian Blur**: Softens an element.
- **Drop Shadow**: Adds depth.

#### Example (Gaussian Blur)
```xml
<svg width="200" height="100">
  <defs>
    <filter id="blur">
      <feGaussianBlur in="SourceGraphic" stdDeviation="5" />
    </filter>
  </defs>
  <circle cx="50" cy="50" r="40" fill="red" filter="url(#blur)" />
</svg>
```

## Shadows
Shadows enhance the depth and realism of SVG elements.

#### Drop Shadow Example
```xml
<svg width="200" height="100">
  <rect x="20" y="20" width="100" height="50" style="fill:blue;filter:url(#drop-shadow)" />
  <defs>
    <filter id="drop-shadow">
      <feDropShadow dx="4" dy="4" stdDeviation="4" flood-color="gray" />
    </filter>
  </defs>
</svg>
```

## Gradients
Gradients create smooth transitions between colors.

### Types
- **Linear Gradient**: Changes color along a straight line.
- **Radial Gradient**: Changes color radiating from the center.

#### Linear Gradient Example
```xml
<svg width="200" height="100">
  <defs>
    <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:rgb(255,255,0);stop-opacity:1" />
      <stop offset="100%" style="stop-color:rgb(255,0,0);stop-opacity:1" />
    </linearGradient>
  </defs>
  <rect width="200" height="100" fill="url(#grad1)" />
</svg>
```

## Combining Effects
Multiple SVG elements and styles can be combined for complex visuals.

#### Example: A Scene with a Gradient Sky and Text
```xml
<svg width="300" height="200">
  <defs>
    <linearGradient id="sky" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:blue;stop-opacity:1" />
      <stop offset="100%" style="stop-color:lightblue;stop-opacity:1" />
    </linearGradient>
  </defs>
  <rect width="300" height="200" fill="url(#sky)" />
  <text x="50" y="100" font-family="Verdana" font-size="24" fill="white">
    SVG is Awesome!
  </text>
</svg>
```

## Advantages of SVG
- **Scalability**: Perfect for responsive design.
- **Interactive**: Easily animated or styled with JavaScript and CSS.
- **Accessibility**: Can include semantic information.
- **Performance**: Lightweight and faster to load than raster images.

## Use Cases
- **Web Design**: Icons, logos, and decorative elements.
- **Data Visualization**: Charts and graphs (e.g., D3.js library).
- **Interactive Applications**: Maps, games, and animations.
