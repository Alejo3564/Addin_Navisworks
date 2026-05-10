# EGIS Smart Tools — Unified Plugin

EGIS Smart Tools is a unified plugin package that bundles multiple EGIS tools into a single installer and ribbon tab.

## 📦 What's Included

This project provides **one DLL** that integrates **three EGIS plugins** under a single ribbon tab:

- **Clash Approver**  
  Approves clashes based on CSV input files.

- **Street View**  
  Displays a georeferenced Google Street View viewer.

- **Property Importer**  
  Imports properties from Excel files.

## 🚀 Installation

1. Download the ZIP file named **`EGISSmartTools`**.
2. Extract the contents.
3. Navigate to the following folder:
4. Double-click **`Install_EGISSmartTools.bat`** to install the plugin.

## 📁 Installation Package Structure

EGIS_SmartTools_Install
├── Install_EGISSmartTools.bat   # Installer script
├── EGISSmartTools.dll
├── Microsoft.Web.WebView2.Core.dll
├── Microsoft.Web.WebView2.WinForms.dll
├── WebView2Loader.dll
├── DocumentFormat.OpenXml.dll
├── RibbonLayout.xaml
└── Images
├── clash_16.png / clash_32.png
├── sv_16.png    / sv_32.png
└── prop_16.png  / prop_32.png

## 🧩 Notes

- Make sure the host application is closed before running the installer.
- All required dependencies are included in the installation package.

    
