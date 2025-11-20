# 🚀 NeoJournal - Hardware Failure Simulation

<div align="center">

![NeoJournal Banner](https://img.shields.io/badge/NeoJournal-Next--Gen%20Digital%20Journal-00d4ff?style=for-the-badge&logo=book&logoColor=white)

[![License](https://img.shields.io/badge/License-MIT-00ff88.svg?style=flat-square)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

**A futuristic digital journal with realistic disk failure simulation for educational purposes**

[Live Demo](#-live-demo) • [Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Documentation](#-documentation)

</div>

---

## 📖 Overview

**NeoJournal** is an innovative web-based journaling application that combines modern UI/UX design with educational hardware failure simulation. Built with vanilla JavaScript, it demonstrates how applications handle storage limitations and disk failures in real-world scenarios.

The application features a stunning cyberpunk-inspired interface with particle effects, smooth animations, and an intuitive user experience. Most importantly, it includes a toggleable **Disk Failure Mode** that simulates `ENOSPC` (No Space Left on Device) errors when content exceeds predefined limits.

### 🎯 Purpose

This project serves multiple purposes:

- **Educational Tool**: Learn how applications handle storage failures
- **Portfolio Showcase**: Demonstrate advanced front-end development skills
- **UX/UI Design**: Showcase modern design principles and animations
- **Error Handling**: Illustrate proper error management in web applications

---

## ✨ Features

### 🎨 User Interface
- **Cyberpunk Aesthetic**: Neon gradients, glassmorphism, and futuristic design
- **Animated Particles**: Dynamic background particle system
- **Responsive Design**: Fully responsive across all device sizes
- **Smooth Transitions**: Polished animations and hover effects
- **Dark Theme**: Easy-on-the-eyes dark color scheme

### 📝 Journal Functionality
- **Rich Text Input**: Title and content fields with character tracking
- **Real-time Statistics**: Word count, character count, and limit visualization
- **Progress Indicators**: Visual feedback with color-coded warnings
- **Entry Archive**: Browse and reload previous journal entries
- **Auto-save to LocalStorage**: Persistent data across sessions

### 💥 Disk Failure Simulation
- **Toggle Failure Mode**: Enable/disable disk failure simulation
- **Character Limit Enforcement**: Set maximum storage capacity (default: 500 chars)
- **Realistic Error Messages**: `ENOSPC` error codes and detailed failure logs
- **Error Banner**: Beautiful error notification system
- **System Logs**: Comprehensive logging with timestamps and error tracking

### 🔧 Technical Features
- **Pure Vanilla JS**: No frameworks or dependencies required
- **LocalStorage Integration**: Client-side data persistence
- **Object-Oriented Design**: Clean, maintainable code architecture
- **Console Logging**: Detailed error logs for debugging
- **Unique User IDs**: Randomly generated user identifiers

---

## 🚀 Live Demo

You can try NeoJournal live at: [**Your GitHub Pages URL**]

Or run it locally by following the [Installation](#-installation) instructions below.

---

## 📦 Installation

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- A local web server (optional, but recommended)

### Option 1: Direct Download
```bash
# Clone the repository
git clone https://github.com/NadeemAhmad3/Hardware_Failure_Simulation.git

# Navigate to the project directory
cd Hardware_Failure_Simulation

# Open index.html in your browser
```

### Option 2: Using a Local Server
```bash
# Using Python
python -m http.server 8000

# Using Node.js (http-server)
npx http-server

# Using PHP
php -S localhost:8000
```

Then navigate to `http://localhost:8000` in your browser.

---

## 🎮 Usage

### Basic Journaling

1. **Enter Your Content**
   - Type a title in the "Entry Title" field
   - Write your journal content in the main text area
   - Watch real-time statistics update (word count, character count)

2. **Save Your Entry**
   - Click the "Save Entry" button
   - Your entry will be stored in LocalStorage
   - View it in the "Entry Archive" panel

3. **Browse Past Entries**
   - Click any entry in the archive to load it
   - Edit and save as a new entry if desired

### Disk Failure Simulation

1. **Enable Failure Mode**
   - Click the "Disk Failure Mode" toggle switch
   - The toggle will turn red and glow when active

2. **Trigger a Failure**
   - Write content exceeding 500 characters (combined title + content)
   - Click "Save Entry"
   - Observe the realistic error banner with `ENOSPC` error code

3. **View System Logs**
   - Click "Show Logs" at the bottom
   - Review detailed error logs with timestamps
   - See JSON-formatted failure reports

### Understanding the Simulation

The disk failure mode simulates a real storage limitation scenario:

```javascript
// When failure mode is ON and content exceeds limit:
{
  "timestamp": "2024-11-20T...",
  "level": "ERROR",
  "user": "CyberWriter1234",
  "docId": "entry_1234567890_abc123",
  "size": 750,
  "errorCode": "ENOSPC",
  "errorMessage": "No space left on device",
  "limitExceeded": 250,
  "failureType": "HARDWARE_FAILURE_SIMULATED"
}
```

---

## 🏗️ Project Structure

```
Hardware_Failure_Simulation/
│
├── index.html              # Main application file (self-contained)
├── README.md              # This documentation

```

---

## 🛠️ Technical Architecture

### Core Components

#### 1. **NeoJournal Class**
The main application controller managing state and interactions:

```javascript
class NeoJournal {
  constructor() {
    this.config = {
      charLimit: 500,
      warningThreshold: 0.8,
      dangerThreshold: 1.0,
      particleCount: 30
    };
    this.state = {
      failureMode: false,
      currentUser: this.generateUserId(),
      logs: [],
      entries: this.loadEntries()
    };
  }
}
```

#### 2. **Key Methods**

| Method | Purpose |
|--------|---------|
| `toggleFailureMode()` | Enable/disable disk failure simulation |
| `saveEntry()` | Validate and save journal entries |
| `triggerDiskFailure()` | Simulate ENOSPC error |
| `performSave()` | Execute successful save operation |
| `updateStats()` | Update real-time character/word counts |
| `addLog()` | Add entries to system log |

### Storage Schema

Entries are stored in LocalStorage with the following structure:

```javascript
{
  "id": "entry_1732147200000_abc123def",
  "title": "My Journal Entry",
  "content": "Today I learned about...",
  "timestamp": "2024-11-20T10:30:00.000Z",
  "size": 245,
  "user": "CyberWriter1234"
}
```

### Design Patterns

- **Singleton Pattern**: Single instance of NeoJournal class
- **Observer Pattern**: Event-driven UI updates
- **Factory Pattern**: Dynamic UI element generation
- **State Management**: Centralized application state

---

## 🎨 Customization

### Changing the Character Limit

```javascript
// In the NeoJournal constructor
this.config = {
  charLimit: 1000,  // Change from 500 to 1000
  // ...
};
```

### Modifying Colors

CSS variables in `:root`:

```css
:root {
  --primary-blue: #00d4ff;      /* Main accent color */
  --secondary-blue: #0066ff;    /* Secondary accent */
  --accent-cyan: #00ffff;       /* Highlights */
  --danger-red: #ff0055;        /* Error states */
  --success-green: #00ff88;     /* Success states */
}
```

### Adjusting Particle Count

```javascript
this.config = {
  particleCount: 50,  // Increase from 30
};
```

---

## 📊 Browser Compatibility

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 90+ | ✅ Fully Supported |
| Firefox | 88+ | ✅ Fully Supported |
| Safari | 14+ | ✅ Fully Supported |
| Edge | 90+ | ✅ Fully Supported |
| Opera | 76+ | ✅ Fully Supported |

**Note**: LocalStorage must be enabled for full functionality.

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

### Ideas for Contributions

- [ ] Add export functionality (JSON, PDF, Markdown)
- [ ] Implement search and filter for entries
- [ ] Add tags/categories for entries
- [ ] Create different failure modes (network, permission errors)
- [ ] Add data encryption for sensitive entries
- [ ] Implement entry versioning/history
- [ ] Add dark/light theme toggle

---

## 🐛 Known Issues

- LocalStorage has a typical limit of 5-10MB (browser dependent)
- Particle animations may impact performance on low-end devices
- No server-side backup (data is client-side only)

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Nadeem Ahmad

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 👨‍💻 Author

**Nadeem Ahmad**

- 📧 Email: [nadeemahmad2703@gmail.com](mailto:nadeemahmad2703@gmail.com)
- 💼 LinkedIn: [linkedin.com/in/nadeem-ahmad3](https://www.linkedin.com/in/nadeem-ahmad3/)
- 🐙 GitHub: [@NadeemAhmad3](https://github.com/NadeemAhmad3)

---

## 🙏 Acknowledgments

- **Font Awesome** - Icon library
- **Google Fonts** - Inter font family
- **Inspiration** - Cyberpunk 2077 aesthetic
- **Community** - GitHub open source community

---

## 📸 Screenshots

### Main Interface
<img width="1894" height="954" alt="image" src="https://github.com/user-attachments/assets/56cba1a4-f8f1-41a7-bb66-d7b2b6d6c898" />


### Disk Failure Simulation
<img width="1887" height="901" alt="image" src="https://github.com/user-attachments/assets/5fc51d0b-5ff3-4022-b318-a224ecc5b02b" />


### System Logs
<img width="1879" height="742" alt="image" src="https://github.com/user-attachments/assets/47fe3013-a3bd-453f-a78b-4a115b40cde9" />


---

## 🔮 Future Enhancements

- [ ] **Cloud Sync**: Optional backend for multi-device sync
- [ ] **Encryption**: End-to-end encryption for entries
- [ ] **Export Options**: PDF, Markdown, JSON export
- [ ] **Rich Text Editor**: Markdown support with preview
- [ ] **Multiple Themes**: Light mode, more color schemes
- [ ] **Mobile App**: React Native or PWA version
- [ ] **Analytics**: Entry statistics and trends
- [ ] **Collaboration**: Shared journals with permissions

---

## 📚 Additional Resources

- [MDN Web Docs - LocalStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [Error Handling Best Practices](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
- [CSS Animations Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)

---

<div align="center">

### ⭐ Star this repository if you find it helpful!

**Made with 💙 by [Nadeem Ahmad](https://github.com/NadeemAhmad3)**

</div>
