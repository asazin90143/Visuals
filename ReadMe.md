# ⚡ Algorithm & PM Visualizer - Cyberpunk Edition ⚡

A stunning, interactive web application that visualizes sorting algorithms and project management methodologies with a cyberpunk aesthetic, powered by p5.js.

![Cyberpunk Theme](https://img.shields.io/badge/Theme-Cyberpunk-ff00ff?style=for-the-badge)
![Tech](https://img.shields.io/badge/Tech-p5.js-ed225d?style=for-the-badge)
![Sound](https://img.shields.io/badge/Sound-Enabled-00ffff?style=for-the-badge)

## 🎯 Features

### Visual Design
- **Cyberpunk Aesthetic** - Deep black background with neon cyan, hot pink, lime green, and electric purple accents
- **Glowing Effects** - CSS shadows and blurred elements create an authentic neon atmosphere
- **Orbitron Font** - Futuristic typography with animated glows
- **Smooth Animations** - 60 FPS rendering using p5.js

### Interactive Controls
- **Dual Mode System** - Toggle between Sorting Algorithms and Project Management methodologies
- **Speed Control** - Adjust visualization speed from 1x to 10x
- **Playback Controls** - Launch, Pause/Resume, and Reset functionality
- **Sound Toggle** - Enable/disable audio feedback
- **Dynamic Dropdown** - Context-sensitive algorithm selection

### Audio System 🔊
- **Pitch-Mapped Sounds** - Higher values produce higher frequencies
- **Event-Based Feedback** - Different sounds for comparing, swapping, and completing
- **Musical Completion** - Chord progression (C-E-G) when algorithms finish
- **Cyberpunk Synthesis** - Uses oscillators for electronic sound design

## 📊 Supported Algorithms

### Sorting Algorithms (18 Total)

#### Fully Implemented (Detailed Visualizations):
1. **Bubble Sort** - O(n²) - Visual bubble comparison with color-coded states
2. **Insertion Sort** - O(n²) - Building sorted portion incrementally
3. **Merge Sort** - O(n log n) - Recursive divide-and-conquer with merge visualization
4. **Quick Sort** - O(n log n) avg - Partition-based with highlighted pivots
5. **Heap Sort** - O(n log n) - Max heap construction and extraction

#### With Placeholder Implementations:
- Selection Sort
- Shell Sort
- Comb Sort
- Cycle Sort
- Gnome Sort
- Cocktail Shaker Sort
- Counting Sort
- Radix Sort
- Bucket Sort
- Pigeonhole Sort
- Bead Sort
- Tim Sort
- Intro Sort

### Project Management Methodologies (19 Total)

#### Fully Implemented (Detailed Visualizations):
1. **Waterfall** - Sequential falling blocks with progress bars
2. **Scrum** - Rotating sprint cycle with backlog and sprint phases
3. **Kanban** - Three-column board with WIP limits and task movement
4. **Agile** - Iterative cycle showing Plan → Build → Review phases
5. **Extreme Programming (XP)** - Interconnected practice bubbles with dynamic movement

#### With Placeholder Implementations:
- Scrumban
- Lean
- DSDM
- CPM/CCPM
- Six Sigma
- Lean Six Sigma
- PRINCE2
- PMBOK
- CPMAI
- Experimentation-Driven
- Human-in-the-Loop
- AI Task Automation
- Predictive Analytics
- Resource Optimization

## 🎨 Visualization Details

### Sorting Color Codes:
- **Cyan** - Unsorted elements
- **White** - Currently comparing
- **Red** - Elements being swapped
- **Green** - Sorted and in final position
- **Pink** - Pivot element (Quick Sort)

### PM Visualization Techniques:
- **Geometric Primitives** - Circles, rectangles, and custom shapes
- **Text Labels** - Embedded descriptions for clarity
- **Dynamic Movement** - Physics-based animations and transitions
- **Progress Indicators** - Real-time progress bars and status updates

## 🚀 Quick Start

### Installation
Simply open the HTML file in any modern web browser. No build process required!

```bash
# Download the file
# Double-click to open in browser
# Or serve with any local server
python -m http.server 8000
```

### Usage

1. **Select Mode** - Click either "SORTING ALGORITHMS" or "PROJECT MANAGEMENT" tab
2. **Choose Algorithm** - Pick from the dropdown menu
3. **Adjust Speed** - Use the slider to control animation speed (1x-10x)
4. **Launch** - Click the 🚀 LAUNCH button to start
5. **Control Playback** - Use PAUSE/RESUME and RESET as needed
6. **Toggle Sound** - Click MUTE/UNMUTE to control audio feedback

### Keyboard Shortcuts
Currently controlled via UI buttons. Keyboard shortcuts can be added as needed.

## 🛠️ Technical Details

### Technologies Used
- **p5.js** (v1.7.0) - Main rendering and animation library
- **p5.sound.js** - Audio synthesis and sound effects
- **HTML5** - Structure and container
- **CSS3** - Styling, animations, and glow effects
- **Vanilla JavaScript** - Application logic and state management

### Architecture

```
State Management:
├── Global state object
├── Mode switching (sorting/PM)
├── Animation data structures
└── Sound system state

Rendering Pipeline:
├── p5.js setup() - Canvas initialization
├── draw() loop - 60 FPS rendering
├── Mode router - Directs to appropriate visualizer
└── Algorithm steppers - Frame-by-frame logic

Sound System:
├── Oscillator synthesis
├── Pitch mapping (200-1000 Hz)
├── Event-based triggers
└── Amplitude control (8-15%)
```

### Performance
- **Frame Rate**: 60 FPS
- **Canvas Size**: 1200x600 pixels
- **Array Size**: 100 elements (sorting)
- **Sound Latency**: <50ms

## 🎵 Sound Design

### Waveform Types:
- **Sine Wave** - Smooth comparison sounds
- **Square Wave** - Sharp swap sounds
- **Triangle Wave** - Sorted element confirmation
- **Sawtooth Wave** - Phase transitions and launches

### Frequency Mapping:
```javascript
Compare: 200-800 Hz (mapped to element values)
Swap: 300-1000 Hz (mapped to element values)
Sorted: 600 Hz (fixed)
Phase: 400 Hz (fixed)
Launch: 200 → 400 → 800 Hz (ascending)
Complete: 523, 659, 784 Hz (C-E-G chord)
```

## 📝 Customization Guide

### Adding New Sorting Algorithms

1. **Add to data object**:
```javascript
const sortingAlgos = {
    'myalgo': { 
        name: 'My Algorithm', 
        desc: 'Description here' 
    }
};
```

2. **Create step function**:
```javascript
function stepMyAlgo() {
    const data = state.animationData;
    // Your algorithm logic
    // Update data.array states
    // Call sound functions
}
```

3. **Add to switch statement**:
```javascript
case 'myalgo':
    stepMyAlgo();
    break;
```

### Adding New PM Methodologies

1. **Add to data object**:
```javascript
const pmMethodologies = {
    'mymethod': { 
        name: 'My Method', 
        desc: 'Description here' 
    }
};
```

2. **Create initialization**:
```javascript
function initMyMethod() {
    state.animationData.elements = [...];
}
```

3. **Create draw function**:
```javascript
function drawMyMethod() {
    // Your visualization logic
    // Use p5.js drawing functions
    // Add text labels
}
```

### Customizing Colors

Edit the CSS variables or inline styles:
```css
--neon-cyan: #00ffff;
--hot-pink: #ff00ff;
--lime-green: #39ff14;
--electric-purple: #bf00ff;
--deep-black: #050505;
```

## 🐛 Troubleshooting

### Sound Not Working
- Ensure browser allows autoplay (click anywhere on page first)
- Check if sound is muted via toggle button
- Verify p5.sound.js is loaded properly

### Animation Lagging
- Reduce speed multiplier
- Close other browser tabs
- Check browser hardware acceleration is enabled

### Canvas Not Displaying
- Check console for JavaScript errors
- Verify p5.js CDN is accessible
- Ensure container div exists with ID "canvasContainer"

## 🎓 Educational Use

This visualizer is perfect for:
- **Computer Science Education** - Teaching algorithm complexity and behavior
- **Project Management Training** - Understanding methodology differences
- **Interactive Learning** - Visual and auditory learning styles
- **Coding Bootcamps** - Demonstrating algorithm efficiency
- **Presentations** - Eye-catching demonstrations

## 📄 License

This project is open source and available for educational and personal use.

## 🤝 Contributing

Contributions welcome! Areas for improvement:
- Additional algorithm implementations
- More PM methodology visualizations
- Enhanced sound design
- Mobile responsiveness
- Accessibility features (screen reader support)
- Keyboard shortcuts
- Algorithm comparison mode
- Step-by-step explanation overlay

## 📬 Contact & Support

For questions, suggestions, or bug reports, please open an issue or reach out to the development team.

---

**Built with 💜 using p5.js | Designed for the future | Powered by algorithms**

*"Where code meets art, and sorting becomes beautiful"*

