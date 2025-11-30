# Bangla TTS Pipeline Architecture Visualization

A visually stunning, interactive simulation of a Bangla Text-to-Speech (TTS) system using Flowtron and HiFi-GAN architecture.

## Features

- **Interactive Pipeline Visualization**: Visual representation of the complete Bangla TTS architecture
- **Real-time Simulation**: Watch the audio generation process from text input to waveform output
- **Detailed Tooltips**: Hover over any component to see detailed information and architectural diagrams
- **Responsive Design**: Works on various screen sizes with adaptive tooltip positioning
- **Speed Control**: Adjustable playback speed to control the simulation pace
- **Beautiful UI**: Modern glass-morphism design with animated elements

## Architecture Overview

The system uses a two-stage approach combining Flowtron (for acoustic modeling) and HiFi-GAN (for neural vocoding):

### Stage 1: Flowtron Acoustic Model
- Converts Bangla text to mel-spectrograms
- Uses affine coupling layers with attention mechanisms
- Generates high-quality alignments between text and audio

### Stage 2: HiFi-GAN Vocoder
- Converts mel-spectrograms to raw audio waveforms
- Multi-stage upsampling for high-fidelity output
- Uses residual blocks with different receptive fields

## Components

### Flowtron Components
- **System Inputs**: Bangla text, Speaker ID, and noise vectors
- **Flowtron Steps**: Affine Coupling layers with LSTM attention mechanisms

### HiFi-GAN Components
- **Pre-Conv1D**: Initial channel expansion from 80 to 512 channels
- **Upsample Block 1**: 8x upsampling with transposed convolution and MRF ResBlock
- **Upsample Block 2**: Additional 8x upsampling for further sequence expansion
- **Post-Conv & Tanh**: Final activation layer for waveform construction
- **Bangla Audio**: Raw waveform output at 22,050Hz

## How to Use

1. Open `index.html` in a modern web browser
2. Click "Start Simulation" to begin the visualization
3. Hover over any component to see detailed information about its function
4. Use the speed control panel to adjust the simulation pace
5. Observe how the system processes inputs through each stage

## Technical Details

- Built with HTML5, CSS3, and JavaScript
- Uses Tailwind CSS for styling with custom animations
- Implements a physics-based tooltip system
- Responsive design with viewport boundary detection
- Simulated animation delays to represent real processing time

## Browser Compatibility

- Modern browsers supporting CSS Grid, Flexbox, and ES6+ JavaScript
- Works best on Chrome, Firefox, Edge, and Safari (latest versions)

## File Structure

```
├── index.html          # Main visualization page
├── README.md          # Project documentation
├── images/            # Architecture diagrams
│   ├── arch.webp        # Flowtron architecture
│   ├── Bangla Audio.webp # Audio output diagram
│   ├── Post-Conv & Tanh.webp # Post-processing diagram
│   ├── Pre-Conv1D.webp # Pre-processing diagram
│   ├── Upsample Block 1.webp # First upsampling block
│   └── Upsample Block 2.webp # Second upsampling block
└── ...
```

## License

This project is open source and available under the MIT License.