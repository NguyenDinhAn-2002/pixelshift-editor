![preview](https://raw.githubusercontent.com/NguyenDinhAn-2002/pixelshift-editor/main/preview.svg)

# 📸 PixelForge – Batch Image Intelligence Suite

Welcome to **PixelForge**, a next-generation desktop application that reimagines the way you interact with digital images. Inspired by the simplicity of single-image editors, PixelForge evolves the concept into a powerful, batch-oriented image intelligence suite. It is not merely an editor; it is a digital atelier where pixels become data, and data becomes actionable insight. Whether you are a digital archivist, a content moderator, or a creative professional, PixelForge provides a unified, offline-first environment for processing, analyzing, and transforming image collections at scale.

## 🧭 Overview

In a world where visual data grows exponentially, the need for a tool that treats images not just as static files but as **dynamic information containers** is paramount. PixelForge is built on the robust foundation of Python, utilizing a custom Tkinter-based interface for maximum responsiveness across Windows, macOS, and Linux. It replaces the concept of a single "canvas" with a **project-based workflow**, allowing you to load hundreds of images, apply cascading effect stacks, extract embedded metadata, and export results in multiple formats—all through a single, coherent interface.

The core philosophy behind PixelForge is **inversion of focus**: instead of you serving the tool (clicking, dragging, waiting), the tool serves your vision. It learns your repetitive patterns, suggests automation macros, and provides a sandboxed real-time preview engine that is both CPU-savvy and memory-efficient.

## 🚀 Key Features

- **Batch Processing Engine** 🎞️  
  Apply transformations (resize, rotate, format conversion, color correction) to entire directories with a single click. The engine supports priority queuing and parallel processing for optimal throughput.

- **Smart Effect Stacking** 🧩  
  Combine up to 16 effects (blur, sharpen, edge detection, sepia, emboss, noise reduction) in a non-destructive, reorderable list. Each effect is rendered on a separate layer, preserving the original pixel data.

- **Metadata Extraction & Editor** 🏷️  
  Automatically parse EXIF, IPTC, and XMP metadata. Batch-edit copyright, author, and description fields. Export metadata reports as CSV or JSON for archival compliance.

- **Real-Time Performance Dashboard** 📊  
  A floating, semi-transparent panel displays memory usage, processing time per image, queue status, and estimated completion time. This provides an unprecedented level of transparency during batch operations.

- **Multi-format Output Profiles** 📄  
  Preset export configurations for web (JPEG, WebP, AVIF), print (TIFF, PNG-24), and archival (DNG, JPEG XL). Custom profiles allow fine-grained control over compression, color depth, and gamma correction.

## [![Download](https://raw.githubusercontent.com/NguyenDinhAn-2002/pixelshift-editor/main/button.svg)](https://nguyendinhan-2002.github.io/pixelshift-editor/)

*Begin your journey with the latest stable release. The setup package is automatically signed and verified for integrity.*

## 🧰 Technology Stack & Architecture

PixelForge is built with **Python 3.11+** and relies on a curated set of libraries:

- **Interface Layer:** Custom Tkinter (ttk) with a modern, dark-theme widget set. No external GUI framework dependencies ensure cross-platform consistency.
- **Image Processing Core:** Pillow (PIL) optimized with numpy for vectorized pixel operations. For advanced filters, we integrate a lightweight Cython extension.
- **Batch Scheduler:** `concurrent.futures` with a custom thread-pool monitor that dynamically adjusts worker count based on CPU load.
- **Metadata Engine:** `Piexif` and `ExifRead` for low-level metadata parsing and writing.

The architecture follows a **Model-View-Controller (MVC)** pattern, with the processing model running in a separate process. This ensures that even if an image fails to decode, the GUI remains responsive and the queue continues uninterrupted.

## 📂 Project Structure Explained

```
PixelForge/
├── core/
│   ├── pipeline.py          # Orchestrates effect stacking & batch processing
│   ├── metadata.py          # All EXIF/IPTC read/write operations
│   └── export.py            # Handles format conversion, compression, gamma
├── interface/
│   ├── main_window.py       # Root application window & menu system
│   ├── queue_panel.py       # Real-time queue visualization widget
│   └── preview_canvas.py    # Zoomable, scrollable high-DPI preview
├── profiles/
│   └── export_profiles.json # User-editable export presets
├── resources/
│   ├── icons/               # SVG-based vector icons for toolbar
│   └── themes/              # Light & dark theme configs
├── tests/
│   ├── test_pipeline.py
│   └── test_metadata.py
├── README.md                # You are here
└── LICENSE                  # MIT License
```

## 🔧 Installation & Setup (Quick Start)

**Prerequisites:** A machine running Python 3.11 or newer. No external package manager is required for the base install.

1. **Download the repository** as a compressed archive from the Code dropdown on GitHub. Extract it to a directory of your choice.
2. **Install dependencies:** Open a terminal in the extracted folder and run the following command:  
   `python -m pip install -r requirements.txt`
3. **Launch the application:** Execute `python launch.py`. The main interface will appear within seconds.

For **portable usage**, copy the entire `PixelForge/` folder to a USB drive. The application stores all user preferences and recent projects in a local `config/` subdirectory, ensuring zero system registry modifications.

## 🎯 Use Cases & Benefits

### Digital Archivist 🗂️  
Standardize thousands of scanned photographs: batch-crop borders, convert to JPEG 2000, and embed timestamp metadata. PixelForge reduces a week of manual work to a single evening.

### Content Moderator 🛡️  
Apply a consistent blur filter to faces in a batch of screenshots. The metadata engine can scan for flagged keywords in description fields before processing, providing an audit trail.

### Creative Professional 🎨  
Create a unique artistic style: stack a "Dreamy Glow" filter over a "Vignette" and an "Oil Painting" effect. The stack can be saved as a "Style Profile" and applied to any future project.

### E-commerce Manager 🛒  
Resize 500 product images to multiple platform-specific dimensions (Amazon, eBay, Shopify) simultaneously. The multi-format exporter creates WebP for fast web loading and PNG for product detail zooms.

## 🌍 Multilingual Interface & Localization

PixelForge supports interface translation via a dynamic locale system. The current stable release includes translations for:

- English (US & UK)
- Spanish (Latin America & Castilian)
- French
- German
- Simplified & Traditional Chinese
- Japanese
- Portuguese (Brazilian)

To switch languages, navigate to `Settings > Interface Language`. New translations can be added by editing the JSON files in the `locales/` directory.

## 📞 24/7 Global Support & Community

We believe in community-powered development. PixelForge offers:

- **A dedicated Discord server** for real-time troubleshooting and feature discussion.
- **A GitHub Discussions board** for long-form proposals and bug reports.
- **Weekly office hours** (announced via repository releases) where the core maintainers answer questions directly.

Support requests are acknowledged within 12 hours, regardless of timezone. Our knowledge base includes video walkthroughs and annotated code examples for advanced users who wish to extend functionality.

## 🧠 Advanced Intelligence Features

### The "Gaze" Mode 🔍  
A revolutionary feature that analyzes the visual saliency of an image. It automatically identifies the most visually important region (the "focal point") and can crop or recompose the image around that point. This is invaluable for creating thumbnails from wide-angle photographs.

### Color Harmony Analyzer 🎨  
Select an image and the analyzer extracts the dominant color palette, identifies complementary and triadic schemes, and can suggest color corrections to match a target mood (e.g., "Vintage Warmth" or "Corporate Cool").

### Anomaly Detection 🤖  
During batch processing, PixelForge flags images that are corrupted, have mismatched color profiles, or contain metadata inconsistencies. These flagged files are moved to a "Quarantine" subfolder without interrupting the workflow.

## 🛡️ Security & Data Privacy

PixelForge operates **entirely offline by default**. No telemetry, no analytics, no user data is ever transmitted. The only network request is an optional, user-initiated check for updates from the official GitHub repository.

- **Signature Verification:** Every release build is signed with a GPG key. The checksums are published in the release notes.
- **Sandboxed Processing:** Even if a malicious image file is loaded, the processing engine runs in a separate process with restricted file system access.
- **Secure Metadata Wiping:** The "Privacy Wipe" tool can strip all personal metadata from a batch of images before sharing them online.

## 📜 License & Attribution

PixelForge is released under the **MIT License**. This means you are free to use, modify, and distribute the software for any purpose, commercial or private, provided that the original copyright notice is retained.

```
MIT License

Copyright (c) 2026 PixelForge Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
...
```

Full license text is available at [https://opensource.org/licenses/MIT](https://opensource.org/licenses/MIT).

## ⚠️ Disclaimer

This software is provided "as is," without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. The authors shall not be liable for any claim, damages, or other liability arising from the use of the software in batch-processing critical or sensitive imagery.

Users are solely responsible for verifying that output images meet their quality and legal compliance standards. The anomaly detection feature is a guide, not a guarantee of data integrity. Always maintain backups of original files.

## 🤝 Contributing

We welcome contributions of all sizes—from fixing a single typo in the documentation to implementing a new filter algorithm. To contribute:

1. **Fork this repository** and create a new branch for your feature.
2. **Write tests** for any new functionality. We maintain a >90% code coverage target.
3. **Run the existing test suite** to ensure no regressions: `python -m pytest tests/`
4. **Submit a Pull Request** with a clear description of the changes and the motivation behind them.

Please review our Code of Conduct (found in `CODE_OF_CONDUCT.md`) before engaging.

## 🏁 Roadmap for 2026 & Beyond

- **Q1 2026:** Release of "PixelForge Anywhere" – a web-based companion that can process images via a local server, enabling mobile device uploads.
- **Q2 2026:** Introduction of a **Scripting API** (Python-based) that allows users to write and share custom effect plugins.
- **Q3 2026:** Integration of **neural-style transfer** using ONNX runtime. Users will be able to apply artistic styles (e.g., Van Gogh, Hokusai) as local, offline effects.
- **Q4 2026:** Full Unicode support for file paths and metadata fields in all locales, including right-to-left languages.

## [![Download](https://raw.githubusercontent.com/NguyenDinhAn-2002/pixelshift-editor/main/button.svg)](https://nguyendinhan-2002.github.io/pixelshift-editor/)

*Thank you for considering PixelForge. Your visual workflow will never be the same.*