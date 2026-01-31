# 🛰️ GNSS Logger Toolkit

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20MATLAB-blue)

> **Complete toolkit for GNSS raw measurements analysis - Android logger app, MATLAB processing tools, and positioning algorithms**

---

## 📖 Table of Contents

- [About](#about)
- [What's Included](#whats-included)
- [Features](#features)
- [Quick Start](#quick-start)
- [GNSSLogger Android App](#gnsslogger-android-app)
- [MATLAB Tools](#matlab-tools)
- [Pseudorange Library](#pseudorange-library)
- [Use Cases](#use-cases)
- [Installation](#installation)
- [Usage Examples](#usage-examples)
- [Technical Details](#technical-details)
- [Contributing](#contributing)
- [License](#license)
- [About the Maintainer](#about-the-maintainer)

---

## 🎯 About

The **GNSS Logger Toolkit** is a comprehensive solution for collecting, analyzing, and processing raw GNSS (Global Navigation Satellite System) measurements from Android devices. This toolkit bridges the gap between raw satellite signals and precise positioning solutions.

### What This Toolkit Provides

✅ **Android App (GNSSLogger)** - Collect raw GNSS measurements from your device  
✅ **MATLAB Analysis Tools** - Process and visualize pseudoranges, position, velocity  
✅ **Position Engine** - Weighted least squares positioning algorithms  
✅ **Carrier Phase Analysis** - Advanced signal processing capabilities  
✅ **Real-time Visualization** - See positioning accuracy in real-time  
✅ **Data Export** - Log measurements for offline analysis  

### Why Use This Toolkit?

**For Researchers:**
- Study GNSS signal characteristics
- Develop new positioning algorithms
- Analyze multipath and interference
- Test receiver performance

**For Developers:**
- Build location-based applications
- Integrate raw GNSS processing
- Implement custom positioning solutions
- Test positioning accuracy

**For Students:**
- Learn GNSS fundamentals
- Understand positioning algorithms
- Experiment with real data
- Practice signal processing

---

## 🧰 What's Included

### 1. **GNSSLogger Android App**
📱 Location: `GNSSLogger/`

Modern Android application with:
- Raw GNSS measurement logging
- Real-time positioning display
- Google Maps integration
- Weighted least squares solver
- Multi-frequency GNSS support
- A-GPS control interface
- CN0 (carrier-to-noise) visualization
- Residual analysis tools

### 2. **MATLAB Processing Tools**
📊 Location: `opensource/`

Comprehensive MATLAB scripts for:
- Reading GnssLogger data files
- Computing pseudoranges
- Weighted least squares positioning
- Velocity estimation
- Carrier phase analysis
- Ephemeris data handling
- Visualization and plotting

### 3. **Pseudorange Library**
🔧 Location: `GNSSLogger/pseudorangelib/`

Android library providing:
- Position computation engine
- GNSS measurement processing
- SUPL server communication
- Ephemeris retrieval
- Error modeling

### 4. **Demo Files**
📁 Location: `opensource/demoFiles/`

Sample GNSS log files for:
- Testing algorithms
- Learning data formats
- Validating implementations
- Example datasets

---

## ✨ Features

### GNSSLogger App Features

#### Core Functionality
- **Multi-GNSS Support**: GPS, GLONASS, Galileo, BeiDou, QZSS
- **Multi-Frequency**: L1, L5, E1, E5a (device dependent)
- **Raw Measurements**: Pseudorange, carrier phase, Doppler, CN0
- **Real-time Processing**: On-device position computation
- **Data Logging**: Export to file for analysis

#### Advanced Features
- **Weighted Least Squares**: Sophisticated positioning algorithm
- **Uncertainty Computation**: Position and velocity error estimates
- **Kalman Filter Comparison**: Compare raw vs. filtered positions
- **Google Maps Display**: Visualize computed vs. reported position
- **A-GPS Control**: Clear and inject assistance data
- **CN0 Monitoring**: Track signal strength by satellite
- **Residual Analysis**: Pseudorange and range-rate residuals
- **AGC Support**: Automatic Gain Control monitoring (Android O+)

#### User Interface
- Clean, intuitive design
- Real-time satellite information
- Interactive maps
- Detailed logging controls
- Performance metrics display
- Top satellites ranking

### MATLAB Tools Features

#### Data Processing
- **Read GNSS Logs**: Parse GnssLogger output files
- **Compute Pseudoranges**: Calculate ranges from raw measurements
- **Position Solution**: Weighted least squares implementation
- **Velocity Estimation**: Doppler-based velocity computation
- **Carrier Phase Analysis**: Advanced signal processing

#### Visualization
- **Skyplot**: Satellite visibility and geometry
- **CN0 Plot**: Signal strength over time
- **Residuals**: Positioning error analysis
- **Position Track**: Geographic trajectory display
- **Time Series**: Measurement evolution

#### Data Management
- **Ephemeris Retrieval**: Automatic download from NASA archives
- **File Handling**: Batch processing capabilities
- **Format Conversion**: Export to various formats
- **Quality Checks**: Data validation and filtering

---

## 🚀 Quick Start

### For Android App Users

1. **Install the App**
   - Download APK from releases
   - Or build from source using Android Studio
   - Grant location permissions

2. **Start Logging**
   - Open GNSSLogger app
   - Tap "Start Log"
   - Move to open sky area for best results
   - Watch real-time positioning

3. **View Results**
   - See position on map
   - Check CN0 values
   - Review satellite count
   - Compare raw vs. Kalman filter

4. **Export Data**
   - Tap "Stop Log"
   - Find log files in device storage
   - Transfer to computer for MATLAB analysis

### For MATLAB Users

1. **Setup Environment**
   ```matlab
   % Add toolkit to MATLAB path
   addpath('~/gnss-toolkit/opensource');
   
   % Verify installation
   help opensource
   ```

2. **Process Demo File**
   ```matlab
   % Edit ProcessGnssMeasScript.m
   dirName = '~/gnss-toolkit/opensource/demoFiles';
   
   % Run the script
   ProcessGnssMeasScript
   ```

3. **Analyze Your Data**
   ```matlab
   % Process your own log file
   logFileName = 'your_gnss_log.txt';
   ProcessGpsMeasScript
   ```

---

## 📱 GNSSLogger Android App

### System Requirements

- **Android Version**: 7.0 (Nougat) or higher
- **Hardware**: Device with GNSS raw measurement capability
- **Permissions**: Location, Storage

### Supported Devices

The app works on devices that provide raw GNSS measurements. Notable devices:
- Google Pixel series (all models)
- Samsung Galaxy S8 and newer
- Huawei Mate 9 and newer
- Xiaomi Mi 8 and newer
- OnePlus 5 and newer

Check if your device supports raw measurements:
https://developer.android.com/guide/topics/sensors/gnss

### Building from Source

```bash
# Clone repository
git clone https://github.com/Ahmed-Refaat/gnss-logger-toolkit.git
cd gnss-logger-toolkit/GNSSLogger

# Open in Android Studio
# File -> Open -> Select GNSSLogger directory

# Build and run
# Run -> Run 'app'
```

### App Architecture

```
GNSSLogger/
├── app/                    # Main application
│   ├── src/main/
│   │   ├── java/          # Java source code
│   │   ├── res/           # Resources (layouts, strings)
│   │   └── AndroidManifest.xml
│   └── build.gradle
├── pseudorangelib/        # Positioning library
│   └── src/main/java/
└── build.gradle           # Project config
```

### Key Classes

**MainActivity.java** - Main app interface  
**GnssContainer.java** - GNSS measurement handling  
**PseudorangePositionVelocityCalculator.java** - Position computation  
**FileLogger.java** - Data logging management  
**ResultFragment.java** - Results display  

---

## 💻 MATLAB Tools

### Installation

1. **Extract Files**
   ```bash
   unzip gnss-logger-toolkit.zip -d ~/gnss-toolkit
   ```

2. **Add to MATLAB Path**
   ```matlab
   addpath('~/gnss-toolkit/opensource');
   savepath;  % Save for future sessions
   ```

3. **Verify Installation**
   ```matlab
   help opensource
   Contents opensource
   ```

### Main Scripts

#### ProcessGnssMeasScript.m
Main processing script for GNSS measurements

**Features:**
- Read GNSS log files
- Compute pseudoranges
- Calculate positions
- Visualize results
- Export data

**Usage:**
```matlab
% Edit dirName in script
dirName = '/path/to/your/logfiles';

% Run script
ProcessGnssMeasScript

% Output:
% - Position solutions
% - Satellite plots
% - CN0 graphs
% - Residual analysis
```

#### ProcessGpsMeasScript.m
Simplified GPS-only processing

**Usage:**
```matlab
% Specify log file
logFileName = 'gps_log_2024_01_31.txt';

% Process
ProcessGpsMeasScript
```

### Key Functions

#### Data Reading
**ReadGnssLog.m** - Parse GnssLogger output files
```matlab
[gnssMeas, ~] = ReadGnssLog('logfile.txt');
```

#### Position Computation
**WlsPvt.m** - Weighted least squares solution
```matlab
[pvt] = WlsPvt(gnssMeas, gpsCal);
```

#### Visualization
**PlotPvt.m** - Plot position, velocity, time
```matlab
PlotPvt(pvt, 'Position Solutions');
```

**PlotCno.m** - Signal strength visualization
```matlab
PlotCno(gnssMeas);
```

#### Ephemeris
**GetNasaHourlyEphemeris.m** - Download ephemeris data
```matlab
[allGpsEph, iono] = GetNasaHourlyEphemeris(year, month, day, hour);
```

### Example Workflow

```matlab
%% 1. Setup
addpath('opensource');

%% 2. Read GNSS log
logFile = 'outdoor_walk_2024.txt';
[gnssMeas, gnssCal] = ReadGnssLog(logFile);

%% 3. Get ephemeris
[year, month, day, hour] = ParseLogTime(gnssMeas);
[allGpsEph, iono] = GetNasaHourlyEphemeris(year, month, day, hour);

%% 4. Compute position
[pvt] = WlsPvt(gnssMeas, gnssCal, allGpsEph, iono);

%% 5. Visualize
figure;
subplot(2,1,1);
PlotPvt(pvt, 'WLS Position Solution');
subplot(2,1,2);
PlotCno(gnssMeas, 'Signal Strength');

%% 6. Export results
writetable(struct2table(pvt), 'position_results.csv');
```

### Platform-Specific Notes

**Windows:**
- Use backslashes `\` in paths
- Ensure uncompress utility available

**Mac:**
- Allow MATLAB in Security & Privacy settings
- Use forward slashes `/` in paths

**Linux:**
- Ensure gzip/uncompress installed
- Check file permissions

---

## 🔧 Pseudorange Library

Android library for GNSS positioning computations.

### Features

- Position calculation from raw measurements
- Multi-GNSS constellation support
- Weighted least squares implementation
- Ionospheric corrections
- Tropospheric corrections
- SUPL server integration

### Integration

Add to your Android project:

```gradle
dependencies {
    implementation project(':pseudorangelib')
}
```

### Usage Example

```java
import com.google.location.lbs.gnss.gps.pseudorange.*;

// Create calculator
PseudorangePositionVelocityCalculator calculator = 
    new PseudorangePositionVelocityCalculator();

// Set measurements
calculator.setGnssMeasurements(measurementEvent);

// Compute position
double[] position = calculator.calculatePositionSolution();

// Get results
double latitude = position[0];
double longitude = position[1];
double altitude = position[2];
```

---

## 💡 Use Cases

### 1. **Research & Development**

```matlab
% Study multipath effects
[gnssMeas, ~] = ReadGnssLog('urban_canyon.txt');
multipath = AnalyzeMultipath(gnssMeas);
PlotMultipathSignature(multipath);
```

### 2. **Algorithm Testing**

```java
// Test new positioning algorithm
MyCustomPositioningAlgorithm algo = new MyCustomPositioningAlgorithm();
algo.setMeasurements(gnssData);
Position result = algo.compute();
```

### 3. **Educational Projects**

```matlab
% Demonstrate dilution of precision
[pvt] = WlsPvt(gnssMeas, gnssCal);
CalculateAndPlotDOP(pvt);
```

### 4. **Performance Benchmarking**

```matlab
% Compare different positioning methods
posWLS = WlsPvt(gnssMeas, gnssCal);
posKalman = KalmanFilter(gnssMeas);
CompareMethods(posWLS, posKalman);
```

---

## 🛠️ Installation

### Prerequisites

**For Android Development:**
- Android Studio 4.0+
- Android SDK API 24+
- Java JDK 8+

**For MATLAB:**
- MATLAB R2016b or newer
- No additional toolboxes required
- Uncompress utility (for ephemeris)

### Full Installation

```bash
# Clone repository
git clone https://github.com/Ahmed-Refaat/gnss-logger-toolkit.git
cd gnss-logger-toolkit

# For Android app
cd GNSSLogger
# Open in Android Studio and build

# For MATLAB
# Add 'opensource' directory to MATLAB path
```

---

## 📚 Usage Examples

### Example 1: Collect and Analyze Data

**Step 1: Collect Data with App**
1. Install GNSSLogger on Android device
2. Go outdoors (clear sky view)
3. Start logging
4. Walk/drive for 5-10 minutes
5. Stop logging
6. Transfer log file to computer

**Step 2: Process in MATLAB**
```matlab
% Read log file
[gnssMeas, gnssCal] = ReadGnssLog('outdoor_log.txt');

% Get ephemeris
[allGpsEph, iono] = GetNasaHourlyEphemeris(2024, 1, 31, 12);

% Compute position
[pvt] = WlsPvt(gnssMeas, gnssCal, allGpsEph, iono);

% Plot trajectory on map
figure;
geoplot(pvt.allLlaDegDegM(:,1), pvt.allLlaDegDegM(:,2), 'r-', 'LineWidth', 2);
title('Computed Trajectory');
geolimits([min(pvt.allLlaDegDegM(:,1))-0.001, max(pvt.allLlaDegDegM(:,1))+0.001], ...
          [min(pvt.allLlaDegDegM(:,2))-0.001, max(pvt.allLlaDegDegM(:,2))+0.001]);
```

### Example 2: Compare Position Sources

```matlab
% Extract WLS position
wlsLat = pvt.allLlaDegDegM(:,1);
wlsLon = pvt.allLlaDegDegM(:,2);

% Extract device reported position (from log)
reportedLat = gnssMeas.Latitude;
reportedLon = gnssMeas.Longitude;

% Calculate differences
latError = wlsLat - reportedLat;
lonError = wlsLon - reportedLon;

% Plot error over time
figure;
subplot(2,1,1);
plot(latError);
ylabel('Latitude Error (degrees)');
title('Position Error: WLS vs Device');

subplot(2,1,2);
plot(lonError);
ylabel('Longitude Error (degrees)');
xlabel('Epoch');
```

### Example 3: Signal Quality Analysis

```matlab
% Read measurements
[gnssMeas, ~] = ReadGnssLog('signal_test.txt');

% Plot CN0 for all satellites
figure;
uniqueSvids = unique(gnssMeas.Svid);
hold on;
for i = 1:length(uniqueSvids)
    svid = uniqueSvids(i);
    idx = gnssMeas.Svid == svid;
    plot(find(idx), gnssMeas.Cn0DbHz(idx), 'DisplayName', sprintf('PRN %d', svid));
end
hold off;
xlabel('Measurement Epoch');
ylabel('CN0 (dB-Hz)');
title('Signal Strength by Satellite');
legend('Location', 'eastoutside');
grid on;
```

---

## 🔬 Technical Details

### GNSS Measurement Types

**Pseudorange** - Distance to satellite (with clock errors)  
**Carrier Phase** - Precise phase measurement (ambiguous)  
**Doppler** - Frequency shift (for velocity)  
**CN0** - Carrier-to-noise density ratio (signal quality)  

### Positioning Algorithm

The toolkit uses **Weighted Least Squares (WLS)** with:
- Iterative solution
- CN0-based weighting
- Ionospheric correction
- Tropospheric correction
- Relativistic effects

**Position Equation:**
```
ρ = √[(x-xs)² + (y-ys)² + (z-zs)²] + c(δt - δts)
```

Where:
- ρ = pseudorange
- (x,y,z) = receiver position
- (xs,ys,zs) = satellite position
- c = speed of light
- δt = receiver clock bias
- δts = satellite clock bias

### Data Format

GNSSLogger outputs CSV-like text files with measurements including:
- Timestamp (GPS time)
- Satellite ID (Svid)
- Constellation type
- Pseudorange (meters)
- Carrier phase (cycles)
- Doppler (Hz)
- CN0 (dB-Hz)
- Various status flags

---

## 🤝 Contributing

Contributions are welcome to improve this toolkit!

### How to Contribute

1. **Report Issues**
   - Bugs in app or scripts
   - Documentation errors
   - Feature requests

2. **Submit Code**
   - Bug fixes
   - New features
   - Performance improvements
   - Documentation updates

3. **Share Data**
   - Interesting log files
   - Test scenarios
   - Performance benchmarks

### Development Guidelines

- Follow existing code style
- Add comments for clarity
- Test thoroughly before submitting
- Update documentation

---

## 📄 License

This project is licensed under the **Apache License 2.0** - see the [LICENSE.txt](LICENSE.txt) file for details.

**Copyright 2026 Ahmed Refaat**

---

## 👤 About the Maintainer

**Ahmed Refaat**

Geospatial data engineer and GNSS specialist focused on satellite positioning, navigation systems, and location-based services. Expert in processing raw GNSS measurements and developing positioning algorithms for modern applications.

### Expertise

- 🛰️ **GNSS Systems**: GPS, GLONASS, Galileo, BeiDou
- 📍 **Positioning Algorithms**: Least squares, Kalman filtering, RTK
- 📱 **Mobile Development**: Android location services
- 📊 **Signal Processing**: MATLAB, Python scientific computing
- 🗺️ **Geospatial Analysis**: GIS, remote sensing, spatial data
- ☁️ **Cloud Platforms**: AWS, Google Cloud geospatial services

### Featured Projects

- **[Earth Data Hub](https://github.com/Ahmed-Refaat/earth-data-hub)** - *Your Gateway to Global Geospatial Intelligence*
- **[Geo-Parquet Toolkit](https://github.com/Ahmed-Refaat/geo-parquet-toolkit)** - *Efficient geospatial data storage*
- **[GNSS Logger Toolkit](https://github.com/Ahmed-Refaat/gnss-logger-toolkit)** - *Complete GNSS measurement tools*

### Connect

- **GitHub**: [@Ahmed-Refaat](https://github.com/Ahmed-Refaat)
- **Repository**: [gnss-logger-toolkit](https://github.com/Ahmed-Refaat/gnss-logger-toolkit)

---

## 🌟 Show Your Support

If this toolkit helps your work:

- ⭐ **Star this repository**
- 🔗 **Share with colleagues**
- 🐛 **Report issues**
- 💡 **Suggest improvements**
- 🤝 **Contribute code**

---

**Enabling precise positioning through raw GNSS measurements** 🛰️

*GNSS Logger Toolkit - From raw signals to precise positions*

*Last Updated: January 2026*
