# MindRoute UI Component Design Guide

This document provides visual representations and design specifications for all MindRoute user interface components. Each section includes layout descriptions, styling details, and component interactions.

## Table of Contents

1. [Main Landing Page](#main-landing-page)
2. [Form Component](#form-component)
3. [Roadmap Grid Display](#roadmap-grid-display)
4. [Roadmap Visualization Page](#roadmap-visualization-page)
5. [Interactive Flowchart](#interactive-flowchart)
6. [Custom Nodes](#custom-nodes)
7. [Tab Navigation](#tab-navigation)
8. [Hierarchy Modal](#hierarchy-modal)
9. [Loading States](#loading-states)
10. [Mobile Responsive Design](#mobile-responsive-design)

---

## Main Landing Page
**File**: `app/pages/mindroute/page.tsx`

### Desktop View
![Homepage Desktop](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/homepage_desktop.png)


### Layout Structure
```
┌─────────────────────────────────────────────────────────────┐
│                    Header Navigation                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│    🎯 MindRoute - Create Your Learning Journey              │
│    Generate personalized roadmaps with AI assistance        │
│                                                             │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│                    [FORM COMPONENT]                         │
│                                                             │
├─────────────────────────────────────────────────────────────┤
│  ✨ Featured Roadmaps                                       │
│                                                             │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐         │
│  │Frontend │  │Data Sci │  │Mobile   │  │Backend  │         │
│  │Developer│  │Track    │  │Dev      │  │Engineer │         │
│  │🔥 120   │  │📊 89    │  │📱 156   │  │⚡ 78    │           │
│  └─────────┘  └─────────┘  └─────────┘  └─────────┘         │
│                                                             │
├─────────────────────────────────────────────────────────────┤
│  🔒 Your Private Roadmaps (If authenticated)                │
│                                                             │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐                      │
│  │My React │  │Python   │  │+ Create │                      │
│  │Journey  │  │ML Path  │  │New      │                      │
│  │📈 45%   │  │🎯 12%   │  │         │                       │
│  └─────────┘  └─────────┘  └─────────┘                      │
└─────────────────────────────────────────────────────────────┘
```

### Design Features
- **Color Scheme**: Dark theme with `#131a19` background and `#2d3d3b` borders
- **Typography**: Clean, modern fonts with proper hierarchy
- **Interactive Elements**: Hover effects on roadmap cards
- **Icons**: Lucide React icons for visual appeal
- **Responsive Grid**: Adaptive layout for different screen sizes

---

## Form Component
**File**: `app/pages/mindroute/_components/form_comp.tsx`

### Visual Layout
```
┌─────────────────────────────────────────────────────────────┐
│  Create Your Personalized Learning Roadmap                  │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐            │
│  │🎯 Goal      │ │⏰ Duration   │ │⚡ Weekly Hrs │            │
│  │Frontend Dev │ │12 Weeks     │ │10 hrs/week  │            │
│  └─────────────┘ └─────────────┘ └─────────────┘            │
│                                                             │
│  ┌─────────────┐ ┌─────────────────────────────┐            │
│  │🏆 Level     │ │📚 Learning Style            │             │
│  │Beginner ▼   │ │Videos & Projects ▼          │            │
│  └─────────────┘ └─────────────────────────────┘            │
│                                                             │
│  ┌─────────────────────────────────────────────────────────┐│
│  │           ✨ Generate Roadmap 🚀                       │ │
│  └─────────────────────────────────────────────────────────┘│
└─────────────────────────────────────────────────────────────┘
```

### Interactive Elements
- **Input Fields**: 
  - Text inputs with placeholder text
  - Dropdowns with custom styling
  - Icons for visual context
- **Validation**: 
  - Red border indicators for errors
  - Error message display
  - Real-time validation feedback
- **Button States**:
  - Disabled: Gray background when form incomplete
  - Active: Green gradient with hover effects
  - Loading: Shimmer animation during submission

### Color Palette
- **Background**: `#1a2321` (Dark green-gray)
- **Borders**: `#2d3d3b` (Medium green-gray)
- **Accent**: `#178d73` (Teal green)
- **Text**: White with gray placeholders
- **Icons**: Color-coded by category (blue, purple, yellow, green, pink)

---

## Roadmap Grid Display
**File**: `app/pages/mindroute/_components/RoadmapGrip.tsx`

### Grid Layout
```
Featured Roadmaps
┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│  🎨 Frontend │ │  📊 Data Sci │ │  📱 Mobile   │ │  ⚡ Backend  │
│  Development│ │  Analytics   │ │  Development │ │  Engineering │
│              │ │              │ │              │ │              │
│  👥 156 users│ │  👥 89 users │ │  👥 203 users│ │  👥 124 users│
│  ⭐ 4.8/5    │ │  ⭐ 4.6/5    │ │  ⭐ 4.9/5    │ │  ⭐ 4.7/5    │
│              │ │              │ │              │ │              │
│  [View Map]  │ │  [View Map]  │ │  [View Map]  │ │  [View Map]  │
└──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘

┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│  🤖 AI/ML    │ │  🔒 Cybersec │ │  🎮 Game Dev │ │  📈 Product  │
│  Engineer    │ │  Specialist  │ │  Unity/UE    │ │  Management  │
│              │ │              │ │              │ │              │
│  👥 94 users │ │  👥 67 users │ │  👥 112 users│ │  👥 78 users │
│  ⭐ 4.9/5    │ │  ⭐ 4.5/5    │ │  ⭐ 4.8/5    │ │  ⭐ 4.6/5    │
│              │ │              │ │              │ │              │
│  [View Map]  │ │  [View Map]  │ │  [View Map]  │ │  [View Map]  │
└──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘
```

### Card Design Features
- **Gradient Backgrounds**: Subtle gradients for visual depth
- **Hover Effects**: Scale and shadow transitions
- **Progress Indicators**: Completion percentages for private roadmaps
- **Category Icons**: Emoji or icon representations
- **Metrics Display**: User count and ratings
- **Call-to-Action**: Prominent "View Map" buttons

---

## Roadmap Visualization Page
**File**: `app/(routes)/roadmap/[libid]/page.tsx`

### Page Layout
```
┌─────────────────────────────────────────────────────────────┐
│  ← Back | Frontend Development Roadmap | Share 🔗 | ⚙️      │
├─────────────────────────────────────────────────────────────┤
│  📋 Roadmap | 📚 Courses | 🛠️ Projects | ❓ FAQ           │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│            [INTERACTIVE FLOWCHART CANVAS]                   │
│                                                             │
│  ┌─────────────────────────────────────────────────────────┐ │
│  │                FLOWCHART AREA                           │ │
│  │                                                         │ │
│  │    Root ──→ HTML ──→ CSS ──→ JavaScript                │ │
│  │     │        │       │          │                      │ │
│  │     │     Elements  Layout   Variables                 │ │
│  │     │        │       │          │                      │ │
│  │   Setup   Semantic  Flexbox   Functions                │ │
│  │            HTML      Grid                               │ │
│  └─────────────────────────────────────────────────────────┘ │
│                                                             │
│  🔍 Zoom Controls | 🗺️ Minimap | 🌳 Hierarchy View          │
└─────────────────────────────────────────────────────────────┘
```

### Key UI Elements
- **Header Bar**: Navigation, title, share button, settings
- **Tab Navigation**: Four main content sections
- **Canvas Area**: Full-screen flowchart with zoom/pan
- **Controls**: Zoom, minimap, view toggles
- **Side Panel**: Node details on selection

---

## Interactive Flowchart
**File**: `_components/CustomNode.tsx` and React Flow integration

### Node Layout Patterns
```
Central Spine Layout:
                    ┌─────────────┐
                    │  Root Topic │
                    └──────┬──────┘
                           │
                    ┌──────▼──────┐
        ┌───────────┤ Main Topic 1├───────────┐
        │           └─────────────┘           │
        │                                     │
   ┌────▼────┐                           ┌───▼────┐
   │ Child A │                           │Child B │
   └─────────┘                           └────────┘
                           │
                    ┌──────▼──────┐
                    │ Main Topic 2│◄───────────┐
                    └─────────────┘            │
                           │                   │
                    ┌──────▼──────┐       ┌───▼────┐
                    │ Main Topic 3│       │Child C │
                    └─────────────┘       └────────┘
```

### Node Visual Design
```
Standard Node:
┌─────────────────────────┐
│    🎯 HTML Basics       │
│                         │
│ Learn fundamental HTML  │
│ elements and structure  │
│                         │
│ ○ Prerequisites: None   │
│ ○ Duration: 2 weeks     │
│ ○ Difficulty: Beginner  │
└─────────────────────────┘

Selected Node:
┌═════════════════════════┐
║    🎯 HTML Basics       ║ ← Highlighted border
║                         ║
║ Learn fundamental HTML  ║
║ elements and structure  ║
║                         ║
║ ✅ Prerequisites: None  ║
║ ⏱️ Duration: 2 weeks    ║
║ 📈 Difficulty: Beginner ║
║                         ║
║ [View Resources] [Mark] ║ ← Action buttons
╚═════════════════════════╝
```

### Color Coding System
- **Root Nodes**: `#1976D2` (Blue) - Primary topics
- **Branch Nodes**: `#7B1FA2` (Purple) - Secondary topics  
- **Leaf Nodes**: `#388E3C` (Green) - Specific skills
- **Completed**: `#FFA726` (Orange) - Progress indication
- **In Progress**: `#F57C00` (Amber) - Current focus

---

## Custom Nodes
**File**: `_components/CustomNode.tsx`

### Node Component Structure
```
Node Anatomy:
┌─────────────────────────┐
│ 🎯 Topic Icon & Title   │ ← Header with icon
├─────────────────────────┤
│ Brief description text  │ ← Content area
│ explaining the topic    │
├─────────────────────────┤
│ ○ Handles for edges     │ ← Connection points
│ ○ Progress indicator    │
│ ○ Difficulty level      │ ← Metadata
└─────────────────────────┘
```

### Interactive States
1. **Default State**: Standard appearance with subtle shadow
2. **Hover State**: Elevated shadow, slight scale increase
3. **Selected State**: Bold border, expanded content area
4. **Completed State**: Green checkmark, strikethrough text
5. **Loading State**: Skeleton animation while content loads

### Handle Positions
- **Top**: `targetPosition: 'top'` - Incoming connections
- **Bottom**: `sourcePosition: 'bottom'` - Outgoing connections  
- **Left**: `sourcePosition: 'left'` - Left-side branches
- **Right**: `sourcePosition: 'right'` - Right-side branches

---

## Tab Navigation
**File**: `_components/tab-navigation.tsx`

### Courses Section - Desktop View
![Courses Section Desktop](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/courses_section_desktop.png)


### Projects Section - Desktop View
![Projects Section Desktop](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/projects_section_desktop.png)


### FAQ Section - Desktop View
![FAQ Section Desktop](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/faq_section_desktop.png)


### Tab Bar Design
```
┌─────────────────────────────────────────────────────────────┐
│ 📋 Roadmap | 📚 Courses | 🛠️ Projects | ❓ FAQ              │
│ ────────── │           │            │                      │ ← Active indicator
└─────────────────────────────────────────────────────────────┘
```

### Tab Content Areas
```
Roadmap Tab:
┌─────────────────────────────────────────────────────────────┐
│                Interactive Flowchart                        │
│  [View Toggle: Flow | Hierarchy]                           │
└─────────────────────────────────────────────────────────────┘

Courses Tab:
┌─────────────────────────────────────────────────────────────┐
│  📚 Recommended Courses                                     │
│                                                             │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐           │
│  │ HTML Course │ │ CSS Mastery │ │ JS Complete │           │
│  │ ⭐ 4.8/5    │ │ ⭐ 4.9/5    │ │ ⭐ 4.7/5    │           │
│  │ Free        │ │ $49         │ │ $79         │           │
│  └─────────────┘ └─────────────┘ └─────────────┘           │
└─────────────────────────────────────────────────────────────┘

Projects Tab:
┌─────────────────────────────────────────────────────────────┐
│  🛠️ Hands-on Projects                                       │
│                                                             │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐           │
│  │ Portfolio   │ │ Todo App    │ │ E-commerce  │           │
│  │ Website     │ │ React/JS    │ │ Full Stack  │           │
│  │ 🟢 Beginner │ │ 🟡 Inter.   │ │ 🔴 Advanced │           │
│  └─────────────┘ └─────────────┘ └─────────────┘           │
└─────────────────────────────────────────────────────────────┘

FAQ Tab:
┌─────────────────────────────────────────────────────────────┐
│  ❓ Frequently Asked Questions                              │
│                                                             │
│  ▶ How long does it take to complete?                      │
│  ▶ What prerequisites do I need?                           │
│  ▶ Can I customize the learning path?                      │
│  ▶ Are there any free alternatives?                        │
└─────────────────────────────────────────────────────────────┘
```

---

## Hierarchy Modal
**File**: `_components/HierarchyModal.tsx`

### Node Click Modal - Desktop View
![Node Click Modal Desktop](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/node_click_modal_desktop.png)


### Project Click Interaction - Desktop View
![Project Section Click Desktop](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/project_section_click_desktop.png)


### Tree Navigation Features
- **Expandable Folders**: Click to expand/collapse sections
- **Progress Indicators**: Checkmarks for completed topics
- **Search Functionality**: Find specific topics quickly
- **Jump to Node**: Click to highlight in flowchart
- **Export Options**: Download as PDF or text outline

---

## Loading States
**File**: `_components/LoadingStatus.tsx`

### Loading Screen Interface
![Loading Screen](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/loading_screen.png)

### Progressive Loading Design
```
Initial Loading:
┌─────────────────────────────────────────────────────────────┐
│                    🤖 Generating Your Roadmap               │
│                                                             │
│  ████████████████████████████████████░░░░░░░░ 75%          │
│                                                             │
│  ✅ Analyzing your learning goals...                       │
│  ✅ Researching optimal learning path...                   │
│  🔄 Generating personalized curriculum...                  │
│  ⏳ Finalizing roadmap structure...                        │
│                                                             │
│              Estimated time: 30-60 seconds                 │
└─────────────────────────────────────────────────────────────┘

Skeleton Loading for Nodes:
┌─────────────────────────┐
│ ████████████████████    │ ← Animated shimmer
│                         │
│ ████████████████        │
│ ████████████            │
│                         │
│ ████████ ████████       │
└─────────────────────────┘
```

### Loading State Variations
1. **Initial Generation**: Progress bar with status messages
2. **Background Updates**: Spinner overlay on existing content
3. **Node Loading**: Skeleton placeholders for individual nodes
4. **Content Loading**: Shimmer animations for text areas
5. **Error States**: Retry buttons with error messages

---

## Mobile Responsive Design

### Mobile Layout Adaptations
```
Mobile View (320px - 768px):
┌─────────────────────┐
│ ☰ MindRoute      🔍 │ ← Hamburger menu
├─────────────────────┤
│                     │
│    Create Roadmap   │
│                     │
│ ┌─────────────────┐ │ ← Stacked form fields
│ │ 🎯 Learning Goal│ │
│ └─────────────────┘ │
│ ┌─────────────────┐ │
│ │ ⏰ Duration     │ │
│ └─────────────────┘ │
│ ┌─────────────────┐ │
│ │ ⚡ Weekly Hours │ │
│ └─────────────────┘ │
│                     │
│ ┌─────────────────┐ │
│ │ Generate Roadmap│ │
│ └─────────────────┘ │
├─────────────────────┤
│                     │
│ Featured Roadmaps   │
│ ┌─────────────────┐ │ ← Single column grid
│ │ Frontend Dev    │ │
│ │ 👥 156 | ⭐ 4.8 │ │
│ └─────────────────┘ │
│ ┌─────────────────┐ │
│ │ Data Science    │ │
│ │ 👥 89  | ⭐ 4.6 │ │
│ └─────────────────┘ │
└─────────────────────┘
```

### Touch-Optimized Interactions
- **Larger Touch Targets**: Minimum 44px buttons
- **Swipe Gestures**: Navigate between tabs
- **Pinch-to-Zoom**: Flowchart scaling
- **Pull-to-Refresh**: Update content
- **Drawer Navigation**: Collapsible side menus

### Responsive Breakpoints
- **Mobile**: 320px - 768px (Single column, stacked layout)
- **Tablet**: 768px - 1024px (Two column, condensed spacing)
- **Desktop**: 1024px+ (Full layout with sidebars)

---

## Design System & Styling

### Color Palette
```
Primary Colors:
┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐
│   #131a19   │ │   #1a2321   │ │   #2d3d3b   │ │   #3c514f   │
│  Background │ │ Input Field │ │   Borders   │ │   Hover     │
└─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘

Accent Colors:
┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐
│   #178d73   │ │   #1976D2   │ │   #7B1FA2   │ │   #F57C00   │
│  Primary    │ │    Blue     │ │   Purple    │ │   Orange    │
└─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘
```

### Typography Scale
- **Heading 1**: 2.5rem, bold, letter-spacing: -0.025em
- **Heading 2**: 2rem, semibold, letter-spacing: -0.025em  
- **Heading 3**: 1.5rem, semibold, letter-spacing: -0.015em
- **Body**: 1rem, regular, line-height: 1.6
- **Caption**: 0.875rem, medium, opacity: 0.8

### Spacing System
- **xs**: 4px (0.25rem)
- **sm**: 8px (0.5rem)
- **md**: 16px (1rem)
- **lg**: 24px (1.5rem)
- **xl**: 32px (2rem)
- **2xl**: 48px (3rem)

### Animation & Transitions
- **Duration**: 200ms for micro-interactions, 300ms for larger changes
- **Easing**: cubic-bezier(0.4, 0, 0.2, 1) for natural feel
- **Hover Effects**: Scale(1.02) with shadow increase
- **Loading States**: Shimmer animations with 1.5s duration

---

## Content Page Layouts

### Desktop Content Page
![Content Page Desktop](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/content_page_desktop.png)


---

## Project Tab Sections

### Prerequisites Section
![Prerequisites Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/prereq_section.png)

### Skills Required Section
![Skills Required Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/skill_required_section.png)

### Key Concepts Section
![Key Concepts Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/key_concept_section.png)

### Learning Outcomes Section
![Learning Outcomes Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/learning_outcomes_section.png)

### Tools Section
![Tools Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/tools_section.png)

### Folder Structure Section
![Folder Structure Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/folder_structure_section.png)

### Prototype Section
![Prototype Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/prototype_section.png)

### Checklist Section
![Checklist Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/checklist_section.png)

### Test Cases Section
![Test Cases Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/Test_cases_section.png)

### Extensions Section
![Extensions Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/extensions_section.png)

### Deployment Guide Section
![Deployment Guide Section](https://raw.githubusercontent.com/sidkr222003/MINDROUTE_DOCUMENTATION/main/UI_IMAGES/Project_tab_sections/deployment_guide_section.png)

This comprehensive UI design guide provides all the visual specifications needed to understand and implement the MindRoute interface components.
