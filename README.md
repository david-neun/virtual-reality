# virtual-reality
# Unity XR Device Position Tracking

![XR Device](./xr_device.png)
![XR Device](./xr_sample.png)

## Overview
This Unity script demonstrates how to track and display the position of an XR input device (such as a VR controller) using Unity's XR Input APIs. The script continuously updates and displays the position values of the specified device on the screen via a UI Text element.

## Features
- **XR Device Tracking**: Continuously obtains the XR device’s current positional data.
- **Real-time UI Display**: Displays device position updates in real-time on the UI.
- **Efficient Input Handling**: Only updates the display text when the device position changes significantly.

## Prerequisites
- Unity Engine (Tested with Unity 2021 or newer)
- XR Plugin Management configured (e.g., Oculus, OpenXR)
- UI Canvas set up with a `Text` UI element

## Setup

1. **Clone the Repository**
```bash
git clone https://github.com/david-neun/virtual-reality.git
```

2. **Setup the Unity Scene**
- Ensure XR support is enabled in your Unity project settings (`Project Settings -> XR Plug-in Management`).
- Create a Canvas and add a Text UI component.  
  **Hierarchy Example**:
  ```
  Canvas
    └── Text (Rename to 'ValoresText' or similar)
  ```

3. **Attach the Script**
- Attach the provided `Track.cs` script to an empty GameObject.
- Assign the created UI Text component (`valores`) from your Canvas to the `valores` field in the script through the Unity inspector.

## Usage
- Run your scene in Play mode with an XR device connected (e.g., Oculus controller).
- The UI Text element will display real-time positional values of the XR device.

## Example Display Output
```
(0.123, 1.456, -0.789)
```

Values represent the XR device’s coordinates in Unity's virtual space (X, Y, Z), formatted to 3 decimal places.

## Code Overview
| Method | Description |
|---|---|
| `GetDevice()` | Retrieves and assigns the XR device to track (left-hand controller in this script). |
| `OnEnable()` | Checks device validity and retrieves device information on script initialization. |
| `Update()` | Continuously fetches the device’s position and updates the UI when changes are detected. |

## Project Structure
```
├── Assets
│   ├── Scripts
│   │   └── Track.cs
│   └── Scenes
│       └── SampleScene.unity
├── Packages
├── ProjectSettings
└── README.md
```

## Dependencies
- UnityEngine.XR
- UnityEngine.UI

## License
This project is available under the MIT License. See `LICENSE` file for details.
