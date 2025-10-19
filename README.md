# Wilderness Workflow Specification

A comprehensive, interactive web-based workflow specification tool for film and video production. This tool helps production teams plan and calculate data requirements, manage camera configurations, and maintain detailed technical specifications.

## Features

### 📹 Camera Management
- **Multi-Camera Support**: Pre-configured for Sony Venice 2, DJI Ronin 4D, and Drone cameras
- **Dynamic Camera Addition**: Add/remove cameras as needed
- **Detailed Specifications**: Complete technical specs for each camera including:
  - Format and codec options
  - Sensor types and resolutions
  - Frame rates
  - Color science settings
  - ND filter configurations
  - ISO settings

### 📊 Data Rate Calculator
- **Real-time Calculations**: Automatic data rate calculations based on camera settings
- **Multiple Timeframes**: Shows data per hour, per day, per week
- **Shooting Ratio**: Accounts for production shooting ratios (3:1 to 50:1)
- **Final Edit Storage**: Estimates storage for final edited content
- **Audio Integration**: Includes production audio in calculations

### ⚙️ Project Settings
- Aspect ratio configuration
- Frame rate settings
- Pixel dimensions
- Audio format specifications
- Master color space
- Time of day timecode format
- Shooting ratio planning

### 📝 Editorial Specifications
- Editorial codec selection (DNxHD/DNxHR/ProRes)
- Resolution options
- Container formats
- LUT and color pipeline settings
- Sync and masking options
- Burn-in configurations
- NLE compatibility
- Metadata formats
- Delivery platform options

### 💾 Persistent Data Storage
- **Auto-Save**: All changes automatically saved to browser localStorage
- **Export/Import**: Share configurations via JSON files
- **Camera State Persistence**: Added/removed cameras persist across sessions
- **Settings Backup**: Export complete workflow configurations

## Live Demo

**GitHub Pages:** `https://YOUR-USERNAME.github.io/wild-workflow/refs/wilderness_workflow_spec.html`

*(Update this URL after deployment)*

## Quick Start

### Option 1: Local Use
1. Clone or download this repository
2. Open `refs/wilderness_workflow_spec.html` in your browser
3. Start configuring your workflow

### Option 2: Local Web Server
```bash
cd wild-workflow
python3 -m http.server 8000
# Open: http://localhost:8000/refs/wilderness_workflow_spec.html
```

### Option 3: Deploy to GitHub Pages
See [Deployment Guide](DEPLOYMENT_GUIDE.md) for detailed instructions.

## File Structure

```
wild-workflow/
├── refs/
│   ├── wilderness_workflow_spec.html    # Main application
│   ├── wilderness_workflow_spec.md      # Markdown specification
│   ├── sony.txt                         # Sony Venice 2 specs
│   └── ronin-4d-specs.md               # DJI Ronin 4D specs
├── DEPLOYMENT_GUIDE.md                  # Deployment instructions
├── README.md                            # This file
└── .gitignore                          # Git ignore rules
```

## Usage

### Configuring Cameras
1. Select camera type from dropdown
2. Adjust format, sensor, and frame rate settings
3. Configure color science and ND filters
4. View real-time data rate calculations

### Adding/Removing Cameras
1. Click "Add Camera" to add additional cameras
2. Choose camera type (Venice 2, Ronin 4D, or Custom)
3. Click "Remove Camera" on any camera to delete it
4. Changes persist automatically

### Export/Import Settings
1. **Export**: Click "Export Settings" to download current configuration
2. **Share**: Send JSON file to team members
3. **Import**: Click "Import Settings" and select a JSON file
4. **Restore**: All settings and camera configurations restore automatically

### Data Rate Planning
- Adjust shooting ratio (default 10:1) for your production style
- View storage requirements per hour, day, and week
- Calculate final edit storage based on shooting ratio
- Plan storage needs for multi-camera setups

## Technical Specifications

### Camera Support
- **Sony Venice 2**: X-OCN formats (XT/ST/LT), 8K/6K sensors
- **DJI Ronin 4D**: ProRes RAW, ProRes 4444 XQ, ProRes 422, H.264
- **Custom Cameras**: Configurable for any camera system

### Supported Formats
- **Video Codecs**: DNxHD, DNxHR, ProRes (all variants), X-OCN, H.264
- **Audio Formats**: Broadcast WAV, LPCM (24-bit/32-bit, 48kHz/96kHz)
- **Containers**: MXF OP-Atom, MXF OP1a, QuickTime MOV
- **Color Spaces**: S-Gamut3.Cine, ACES, Rec.709, Rec.2020, DCI-P3

### Browser Compatibility
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Data Persistence

All settings are automatically saved to browser localStorage:
- Project settings
- Camera configurations
- Added/removed cameras
- Editorial preferences

Export your settings regularly to:
- Share with team members
- Create backups
- Version control configurations

## Production Workflow

### Pre-Production
1. Configure project settings (aspect ratio, frame rate, etc.)
2. Add all cameras to be used
3. Set shooting ratio based on production type
4. Export configuration for team review

### During Production
1. Import latest configuration
2. Monitor data rates in real-time
3. Adjust settings as needed
4. Export daily configurations for records

### Post-Production
1. Reference editorial specifications
2. Follow delivery requirements
3. Use metadata conventions
4. Maintain configuration history

## Contributing

This is a production workflow tool. To suggest improvements:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## Support

For issues or questions:
- Open an issue on GitHub
- Check the [Deployment Guide](DEPLOYMENT_GUIDE.md)
- Review the inline help text in the application

## License

This project is provided as-is for production use.

## Acknowledgments

- Camera specifications based on manufacturer documentation
- Data rate calculations based on industry standards
- Workflow based on professional production best practices

---

**Version:** 1.0
**Last Updated:** 2025-10-19
**Maintained by:** Production Team

## Quick Links

- [Deployment Guide](DEPLOYMENT_GUIDE.md)
- [Sony Venice 2 Specs](refs/sony.txt)
- [DJI Ronin 4D Specs](refs/ronin-4d-specs.md)
- [Workflow Specification](refs/wilderness_workflow_spec.md)
