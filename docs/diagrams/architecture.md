# System Architecture Diagram

## Architecture Overview

```mermaid
graph TB
    User["👤 User/Client<br/>Browser"]
    
    User -->|HTTPS| CDN["🌐 CDN/Hosting<br/>Netlify/Vercel/GitHub Pages"]
    
    CDN --> HTML["📄 HTML Files<br/>index.html + 15 pages"]
    CDN --> CSS["🎨 CSS3<br/>styles.css<br/>~5000 lines"]
    CDN --> JS["⚡ JavaScript<br/>6 .js files<br/>Vanilla, no frameworks"]
    CDN --> IMG["🖼️ Images<br/>116+ optimized<br/>JPG/PNG/SVG"]
    
    HTML --> Parser["🔄 DOM Parser"]
    CSS --> Render["🎨 CSS Engine"]
    JS --> Runtime["⚙️ JS Runtime"]
    IMG --> Loader["📦 Image Loader"]
    
    Parser --> DOM["🌳 DOM Tree"]
    Render --> Layout["📐 Layout Engine"]
    Runtime --> Events["🎯 Event Handlers"]
    Loader --> Images["🖼️ Rendered Images"]
    
    DOM --> Browser["🔍 Browser Rendering"]
    Layout --> Browser
    Events --> Browser
    Images --> Browser
    
    Browser --> Display["💻 User Display"]
    
    User -->|Interaction| Events
    
    style User fill:#e1f5ff
    style CDN fill:#c8e6c9
    style HTML fill:#fff9c4
    style CSS fill:#ffe0b2
    style JS fill:#f8bbd0
    style IMG fill:#e1bee7
    style Display fill:#e1f5ff
```

---

## Page Load Flow

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server
    participant Cache
    
    User->>Browser: Navigate to URL
    Browser->>Server: Request HTML
    Server->>Cache: Check cache
    Cache-->>Browser: Return cached HTML
    Browser->>Browser: Parse HTML
    Browser->>Server: Request CSS
    Server-->>Browser: Return CSS
    Browser->>Browser: Parse CSS, apply styles
    Browser->>Server: Request JS
    Server-->>Browser: Return JS
    Browser->>Browser: Execute JS
    Browser->>Server: Request Images (lazy)
    Server-->>Browser: Return Images
    Browser->>Browser: Render complete
    Browser-->>User: Display page
    
    Note over Browser: Page Interactive
```

---

## Component Hierarchy

```mermaid
graph TD
    App["🎓 Portfolio App"]
    
    App --> Header["Header Component"]
    App --> Main["Main Content"]
    App --> Footer["Footer Component"]
    
    Header --> Logo["Logo/Branding"]
    Header --> Nav["Navigation"]
    Header --> LangSwitch["Language Switcher"]
    
    Nav --> DesktopNav["Desktop Menu"]
    Nav --> MobileNav["Mobile Menu"]
    
    Main --> Hero["Hero Section"]
    Main --> Content["Content Sections"]
    Main --> Gallery["Gallery"]
    
    Hero --> BG["Background Image"]
    Hero --> Slider["Text Slider"]
    Hero --> CTA["CTA Buttons"]
    
    Content --> Cards["Card Grids"]
    Content --> Stats["Statistics"]
    Content --> Features["Features"]
    
    Gallery --> ImageGrid["Image Grid"]
    Gallery --> Lazy["Lazy Loading"]
    
    Footer --> Contact["Contact Info"]
    Footer --> Links["Quick Links"]
    Footer --> Social["Social Links"]
```

---

## JavaScript Module Dependencies

```mermaid
graph LR
    main["main.js<br/>Core"]
    contact["contact.js<br/>Forms"]
    i18n["i18n.js<br/>Language"]
    translations["translations.js<br/>Strings"]
    blog["blog.js<br/>Blog"]
    tilt["tilt.js<br/>3D Effects"]
    
    main --> contact
    main --> i18n
    main --> blog
    main --> tilt
    i18n --> translations
    
    contact -->|Form Validation| Form["Form Handler"]
    contact -->|Error Messages| UI["UI Update"]
    
    i18n -->|Detect Language| Lang["Language Detector"]
    i18n -->|Switch Language| DOM["DOM Updater"]
    
    style main fill:#bbdefb
    style contact fill:#c8e6c9
    style i18n fill:#ffe0b2
    style translations fill:#f8bbd0
    style blog fill:#e1bee7
    style tilt fill:#ffccbc
```

---

## Data Flow - Form Submission

```mermaid
graph TD
    User["User Fills Form"]
    User --> Submit["Click Submit"]
    Submit --> Validate["Client Validation<br/>contact.js"]
    
    Validate --> CheckRequired["Check Required Fields"]
    CheckRequired --> Valid1{Valid?}
    
    Valid1 -->|No| ShowError["Show Error Messages<br/>Highlight Fields"]
    ShowError --> User
    
    Valid1 -->|Yes| CheckEmail["Validate Email"]
    CheckEmail --> Valid2{Valid?}
    
    Valid2 -->|No| ErrorEmail["Show Email Error"]
    ErrorEmail --> User
    
    Valid2 -->|Yes| CheckSpam["Check Honeypot"]
    CheckSpam --> Valid3{Valid?}
    
    Valid3 -->|No| Block["Block Submission"]
    
    Valid3 -->|Yes| Loading["Show Loading State"]
    Loading --> Submit2["Submit Form"]
    Submit2 --> Service["Form Service<br/>FormSubmit.co"]
    
    Service --> Response["Receive Response"]
    Response --> Check{Success?}
    
    Check -->|Yes| Success["Show Success Message<br/>Clear Form"]
    Check -->|No| Error["Show Error Message<br/>Enable Retry"]
    
    Success --> End["Done"]
    Error --> User
    
    style User fill:#e8f5e9
    style End fill:#c8e6c9
    style ShowError fill:#ffcdd2
    style Success fill:#c8e6c9
```

---

## Responsive Layout Breakpoints

```mermaid
graph LR
    Mobile["📱 Mobile<br/>< 768px<br/>Single Column"]
    Tablet["📱 Tablet<br/>768px - 1024px<br/>2-3 Columns"]
    Desktop["🖥️ Desktop<br/>> 1024px<br/>3-4 Columns"]
    Large["🖥️ Large<br/>> 1440px<br/>Full Width"]
    
    Mobile -->|Expand| Tablet
    Tablet -->|Expand| Desktop
    Desktop -->|Expand| Large
    
    style Mobile fill:#bbdefb
    style Tablet fill:#fff9c4
    style Desktop fill:#c8e6c9
    style Large fill:#f8bbd0
```

---

**Last Updated**: June 1, 2026  
**Format**: Mermaid Diagrams
