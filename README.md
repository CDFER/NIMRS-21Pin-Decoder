# NIMRS-21Pin-Decoder

![PCB Render](Images/Render-Angled.avif)

A miniature DCC decoder for model railways featuring an ESP32-S3 microcontroller, designed to fit standard 21-pin sockets. Includes motor control, sound output, and lighting control in a 30x15.5mm footprint (following NMRA spec).

## Features

- **Compact Design**: 30mm × 15.5mm × 1.0mm 4-layer PCB
- **Power Management**: Dual TPS63070 buck-boost converters for stable 9V (motor) and 3.3V (logic) supplies
- **Quiet Operation**: DRV8213 motor driver with real-time adjustable off-time current regulation
- **Audio System**: MAX98357A I2S amplifier driving 4-8Ω speaker
- **Wireless Capable**: U.FL antenna connector for ESP32-S3's Wi-Fi
- **DCC Compatibility**: Handles ~15V square wave AC input

## Technical Specifications

### Core Components

- **MCU**: ESP32-S3FN8 (240MHz dual-core, 8MB embedded flash)
- **Motor Driver**: [TI DRV8213](https://www.ti.com/lit/ds/symlink/drv8213.pdf)
- **Audio Amplifier**: [MAX98357A](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX98357A-MAX98357B.pdf)
- **Power Regulation**: Dual [TPS63070](http://www.ti.com/lit/ds/symlink/tps63070.pdf) buck-boost converters

### PCB Stackup

1. Top Layer: Signals with GND pour
2. Inner 1: Full GND plane
3. Inner 2: Signals with 3V3 pour
4. Bottom Layer: GND plane with sparse signals

![PCB Layers](Images/PCB-Layers_1-4.avif)

## Design Highlights

- Single-sided assembly and 0.3/0.4mm for cost efficiency
- Optimized ground planes for EMI reduction
- Decoupling buck-boost for stable motor PWM operation
- WiFi + BT support with U.FL antenna

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/CDFER/NIMRS-21Pin-Decoder.git
   ```

2. Open in KiCad v9.0+
3. Review design files:
   - [Interactive PCB Viewer](https://kicanvas.org/?github=https%3A%2F%2Fgithub.com%2FCDFER%2FNIMRS-21Pin-Decoder)
   - [Schematic](Images/Schematic.avif)
   - [PCB Layout](Images/PCB-All-Layers.avif)

## Repository Structure

```
├── Custom_Footprints.pretty  # Custom component footprints
├── Datasheets               # Component technical documents
├── Images                   # PCB visuals and renders
├── LICENSE
└── README.md
```

For those wondering the 21-Pin decoder socket uses a 1.27mm, 22Pin back entry connector and I am using the ```BD050-22-A-0-0500-L-D``` from GCT (the CAD file, footprint and symbol can be found in the custom footprints library I have made).

![Top View](Images/Render-Top.avif)

## License

MIT License - See [LICENSE](LICENSE) for details.

## Contributing

Pull requests welcome! Please discuss major changes via issues first.
