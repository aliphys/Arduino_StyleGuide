# Rules
- Documentation Structure:
  - Each Arduino library should have a README.md in the main folder, introducing the library.
  - A docs folder should contain detailed documentation, including an assets folder for images and other assets, and an api.md file for class and function documentation.
  - The docs/README.md provides an overview of library features and usage.
- Code should be documented inside code, in alignment with `01-acceptable-formats.md`

# Examples
- Main `README.md` 
  - ```
    # 📹 Library for Arduino Supported Cameras

    The Arduino camera library captures pixels from supported cameras on Arduino boards and stores them in a buffer for continuous retrieval and processing.

    📖 For more information about this library please read the documentation [here](./docs/).

    ```
- `docs\README.md`
  - ```
    # Arduino Camera Library
    [![License](https://img.shields.io/badge/License-LGPLv3-blue.svg)](LICENSE)

    The Arduino camera library is designed to capture pixels from cameras on supported Arduino products...

    ## Features
    - Captures pixels and stores them in a frame buffer
    - Store frame buffer on external RAM

    ## Usage
    To use this library, include the camera library in your Arduino sketch...

    ## API
    The API documentation can be found [here](./api.md).

    ## License
    This library is released under the LGPLv3 license.

    ```
- Context in code comments with Javadoc style
  - ```
    /**
    * Connects to a WiFi network of one of the supported types: WPA, WPA2, WEP. 
    * The function is blocking and times out after 10 seconds if no connection could be established. 
    * Use `getErrorMessage()` to retrieve failure reason.
    * 
    * @param ssid The network's SSID.
    * @param password The network password.
    **/
    bool connect(String ssid, String password);

    ```

# Reasoning
This structure is required as part of the Documentation generation infrastructure to display the library information on the Docs website.