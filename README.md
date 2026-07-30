# Real-Time Biomedical Signal Acquisition and Preprocessing System

A real-time embedded biomedical signal acquisition and preprocessing system developed using the **STM32F767 ARM Cortex-M7 microcontroller** and the **ADS1299 24-bit Analog Front-End (AFE)**. The system simultaneously acquires **ECG, EMG, and EOG** signals, performs real-time digital signal preprocessing, and transmits processed data for visualization and analysis.

---

# Project Overview

This project demonstrates the implementation of a high-performance embedded biomedical signal processing platform capable of acquiring multiple physiological signals in real time. The STM32F767 communicates with the ADS1299 through the SPI interface, processes the acquired signals using lightweight digital filters, stores processed samples in circular buffers, and transmits the results through UART for real-time monitoring.

The system is designed for biomedical research, wearable healthcare devices, medical instrumentation, and embedded digital signal processing applications.

---

# Features

- Real-time acquisition of ECG, EMG, and EOG signals
- ADS1299 24-bit Analog Front-End for biomedical signal acquisition
- STM32F767 ARM Cortex-M7 based embedded processing
- High-speed SPI communication
- Real-time digital signal preprocessing
- ECG baseline wander removal
- EMG DC removal and full-wave rectification
- EOG low-pass filtering
- Circular buffer implementation
- High-speed UART data transmission
- Real-time waveform visualization
- Modular and scalable embedded architecture

---

# Hardware Components

- STM32F767 Discovery Board
- ADS1299 24-bit Analog Front-End
- Biomedical Electrodes
- USB-UART Interface
- Personal Computer

---

# Software Tools

- STM32CubeIDE
- STM32 HAL Drivers
- Embedded C
- UART Serial Plotter
- Python / MATLAB (Visualization)

---

# System Architecture

```
Biomedical Electrodes
        │
        ▼
 ADS1299 Analog Front-End
        │
        ▼
  SPI Communication
        │
        ▼
 STM32F767 Cortex-M7
        │
        ├───────────────┐
        │               │
        ▼               ▼
 Signal Processing   Circular Buffer
        │               │
        └───────┬───────┘
                ▼
        UART Communication
                │
                ▼
      PC Visualization Software
```

---

# Signal Processing Pipeline

## ECG Processing

- DC Offset Removal
- Baseline Wander Removal
- First-Order IIR High-Pass Filter

## EMG Processing

- Fast DC Offset Removal
- Full-Wave Rectification
- Muscle Activation Envelope Extraction

## EOG Processing

- First-Order IIR Low-Pass Filter
- Eye Movement Smoothing
- Noise Reduction

---

# Communication Interfaces

## SPI

- Interface between STM32F767 and ADS1299
- SPI Mode 1
- 27-byte acquisition frame
- 24-bit ADC samples

## UART

- USART3
- Baud Rate: **921600 bps**
- ASCII formatted output
- Real-time waveform transmission

---

# ADS1299 Configuration

| Parameter | Value |
|-----------|-------|
| ADC Resolution | 24-bit |
| Sampling Rate | 1000 SPS |
| Active Channels | ECG, EMG, EOG |
| PGA Gain | 24 |
| Interface | SPI |

---

# STM32F767 Configuration

| Parameter | Value |
|-----------|-------|
| MCU | STM32F767 |
| Core | ARM Cortex-M7 |
| Clock Frequency | 216 MHz |
| SPI | SPI1 |
| UART | USART3 |

---

# System Workflow

1. Initialize STM32 peripherals.
2. Configure ADS1299 registers.
3. Start continuous ADC conversion.
4. Wait for DRDY signal.
5. Read 27-byte SPI data frame.
6. Reconstruct 24-bit ADC samples.
7. Process ECG, EMG, and EOG signals.
8. Store processed samples in circular buffers.
9. Transmit processed data through UART.
10. Visualize waveforms on the host computer.

---

# Performance

| Parameter | Value |
|-----------|-------|
| Sampling Rate | 1000 SPS |
| ADC Resolution | 24-bit |
| MCU Frequency | 216 MHz |
| UART Speed | 921600 bps |
| Buffer Size | 1000 Samples |
| ECG Filter | High-Pass IIR |
| EMG Filter | DC Removal + Full-Wave Rectification |
| EOG Filter | Low-Pass IIR |

---

# Applications

- Biomedical Signal Acquisition
- ECG Monitoring Systems
- EMG Monitoring Systems
- EOG Monitoring Systems
- Wearable Medical Devices
- Embedded Healthcare Systems
- Biomedical Research
- Digital Signal Processing

---

# Future Scope

- Multi-channel EEG acquisition
- Wireless data transmission
- Machine learning integration
- Arrhythmia detection
- Real-time patient monitoring
- Cloud connectivity
- Mobile application support
- SD card data logging

---

# Technologies Used

- Embedded C
- STM32 HAL
- ARM Cortex-M7
- ADS1299
- SPI
- UART
- Digital Signal Processing (DSP)
- Circular Buffer
- Real-Time Embedded Systems

---

# Repository Structure

```
Vital-Signal-Preprocessing/
│
├── Docs/
├── Source/
├── Inc/
├── Drivers/
├── STM32CubeIDE Project
└── README.md
```

---

# Author

**Arpitha Eslavath**

B.Tech – Electronics and Communication Engineering (ECE)

**Skills:** Embedded Systems, STM32, ARM Cortex-M, Embedded C, Biomedical Signal Processing, SPI, UART, Digital Signal Processing (DSP)

---

## License

This project is intended for educational and research purposes.
