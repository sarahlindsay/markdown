# Product Requirements Document (PRD)  
## Simple Markdown Editor for macOS  

---

### 1. Overview  
#### Product Name  
Markdown  

#### Product Description  
Markdown is a lightweight, minimalistic macOS application designed to view and edit Markdown files. It prioritizes speed, simplicity, and a distraction-free user experience, differentiating itself from feature-heavy editors by focusing solely on core Markdown functionality.  

#### Objective  
To provide macOS users with a fast, no-frills tool for working with Markdown files, optimized for performance and ease of use.  

#### Target Audience  
- Writers, developers, and note-takers who use Markdown regularly.  
- Users seeking a lightweight alternative to bloated text editors.  
- macOS users who value simplicity and native integration.  

---

### 2. Features  

#### 2.1 Core Functionality  
- **Markdown Viewing**: Render Markdown files in a clean, readable format with real-time preview.  
- **Markdown Editing**: Allow users to edit Markdown text in a plain-text editor with basic syntax highlighting.  
- **File Management**:  
  - Open existing `.md` files from the local filesystem.  
  - Save edited Markdown files to the local filesystem.  
  - Support "Save As" to create new files or overwrite existing ones.  
- **Live Preview**: Display a split-screen view with the editor on one side and a rendered preview on the other, updating in real-time as the user types.  

#### 2.2 User Interface  
- **Minimalist Design**:  
  - Single-window app with a clean, native macOS look and feel.  
  - System default color scheme (supports light/dark mode automatically).  
  - No unnecessary toolbars or menus beyond essential controls.  
- **Layout**:  
  - Default split-screen: Editor (left), Preview (right).  
  - Adjustable split view ratio.  
  - Toggle option to switch between full-screen editor or full-screen preview.  
- **Typography**:
  - JetBrains Mono as default font.  
  - Slightly larger than standard size for better readability.  
- **Controls**:  
  - Menu bar with File (Open, Save, Save As, Quit) and Edit (Undo, Redo, Cut, Copy, Paste) options.  
  - Basic keyboard shortcuts (e.g., Cmd + S for Save, Cmd + O for Open).  
  - Ability to change text size.

#### 2.3 Performance Requirements  
- **Lightweight**: Target app size under 10MB and minimal memory usage (<50MB at idle).  
- **Fast Startup**: Launch in under 1 second.  
- **Responsive**: Real-time preview updates with no noticeable lag (<100ms).  

#### 2.4 Supported Formats  
- Standard Markdown syntax (e.g., headers, lists, bold, italic, links, code blocks).  
- Optional: Basic support for GitHub Flavored Markdown (e.g., tables, strikethrough).  

---

### 3. Technical Specifications
- **Platform**: macOS 14+ (Latest version for simplified development)
- **Architecture**: Document-based app (native macOS document handling)
- **Framework**: SwiftUI with NSTextView for editor
- **Dependencies**: 
  - Down for Markdown parsing
  - Native TextKit for preview rendering
- **Distribution**: Standalone DMG installer
- **Updates**: Manual updates only (no auto-update mechanism)

---

### 4. Out of Scope  
- Advanced Markdown extensions (e.g., LaTeX, diagrams).  
- Cloud sync or collaboration features.  
- Plugin or theme support.  
- Multi-document tabbed interface.  
- App Store distribution
- Custom color schemes
- Auto-update mechanism

---

### 5. Implementation Phases

1. **Basic App Setup** ✅ (Completed)
   - Create SwiftUI document-based app ✅
   - Set up window management ✅
   - Integrate JetBrains Mono font ✅
   - Configure app settings ✅

2. **Editor Implementation** ✅ (Completed)
   - Implement text editing ✅
   - Configure font settings ✅
   - Add file handling ✅
   - Add keyboard shortcuts ✅
   - Add text size controls ✅

3. **Markdown Processing** (In Progress)
   - Integrate Down parser ✅
   - Implement preview rendering ✅
   - Set up preview sync ✅
   - Enhance markdown styling
   - Add GitHub Flavored Markdown support (optional)

4. **Split View Implementation** ✅ (Completed)
   - Create adjustable split view ✅
   - Add view mode toggles (full editor/preview) ✅
   - Implement view persistence
   - Add resize functionality ✅

5. **Polish & Optimization** (Not Started)
   - Implement error handling
   - Optimize performance
   - Add state persistence
   - Final testing

6. **Distribution Prep** (Not Started)
   - Create DMG builder
   - Basic documentation
   - System testing

Updated Timeline: 
- Completed: Basic App Setup, Editor Implementation, Core Split View
- In Progress: Markdown Processing
- Remaining: Polish & Distribution (5-7 days)

---

### 6. Success Metrics  
- App launches successfully on macOS 14+
- Positive user feedback on simplicity and performance
- Achieves performance goals (size <10MB, startup <1s)
- Smooth preview updates (<100ms lag)

---

### 7. User Stories  
- **As a writer**, I want to open a Markdown file and see its rendered output, so I can review my work without switching apps.  
- **As a developer**, I want a lightweight editor to quickly edit Markdown notes, so I don't waste time with slow, bloated tools.  
- **As a minimalist**, I want a simple interface with no distractions, so I can focus on my writing.  

---

### 8. Technical Considerations  
- **Language**: Swift (recommended for native macOS integration).  
- **Framework**: SwiftUI for rapid development and modern UI, or AppKit for finer control.  
- **Markdown Parsing**: Use a lightweight library (e.g., `cmark` or `Down`) or implement a basic parser.  
- **Rendering**: Leverage WebView for preview or native text rendering for speed.  

---

### 9. Open Questions  
- Should basic GitHub Flavored Markdown support be included in the MVP?  
- Is distribution via the Mac App Store worth the overhead, or should it be a standalone `.dmg`?  

---