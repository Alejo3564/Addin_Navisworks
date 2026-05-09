# EGIS Smart Tools — Unified Plugin

## Qué hay en este proyecto

Un solo DLL que contiene los 3 plugins EGIS bajo una única pestaña ribbon:
- **Clash Approver** — aprueba interferencias desde CSV
- **Street View** — visor Google Street View georreferenciado
- **Property Importer** — importa propiedades desde Excel

---

## PASO OBLIGATORIO antes de compilar: ajustar namespaces

Los archivos .cs copiados de los proyectos anteriores tienen sus propios
namespaces. Hay que actualizarlos para que coincidan con la nueva estructura.

### ClashApprover\ClashApproverControl.cs
Cambia la primera línea de namespace:
```
// ANTES:
namespace ClashApprover

// DESPUÉS:
namespace EGISSmartTools.ClashApprover
```

### StreetView\Forms\StreetViewPanel.cs
```
// ANTES:
namespace EGISStreetView.Forms

// DESPUÉS:
namespace EGISSmartTools.StreetView.Forms
```

### StreetView\Core\CoordinateTransformer.cs
```
// ANTES:
namespace EGISStreetView.Core

// DESPUÉS:
namespace EGISSmartTools.StreetView.Core
```

### PropertyImporter\Core\*.cs (ExcelReader, GuidExporter, PropertyWriter)
```
// ANTES:
namespace Egis.PropertyImporter.Core

// DESPUÉS:
namespace EGISSmartTools.PropertyImporter.Core
```

### PropertyImporter\Models\PropertyRow.cs
```
// ANTES:
namespace Egis.PropertyImporter.Models

// DESPUÉS:
namespace EGISSmartTools.PropertyImporter.Models
```

### PropertyImporter\UI\ImporterForm.cs
```
// ANTES:
namespace Egis.PropertyImporter.UI

// DESPUÉS:
namespace EGISSmartTools.PropertyImporter.UI
```

---

## Compilar y desplegar

```powershell
cd D:\2_ALEJO\APP_BIM\NAVISWORKS\EGISSmartTools
.\Deploy.ps1
```

---

## Estructura de deploy

```
%APPDATA%\Autodesk\Navisworks Manage 2026\Plugins\EGISSmartTools\
├── EGISSmartTools.dll
├── Microsoft.Web.WebView2.Core.dll
├── Microsoft.Web.WebView2.WinForms.dll
├── WebView2Loader.dll
├── DocumentFormat.OpenXml.dll
├── RibbonLayout.xaml
├── Images\
│   ├── clash_16.png / clash_32.png
│   ├── sv_16.png    / sv_32.png
│   └── prop_16.png  / prop_32.png
└── en-US\
    ├── RibbonLayout.xaml
    └── Images\ (mismos iconos)
```

---

## Eliminar plugins anteriores

Una vez que el nuevo DLL funcione, elimina estas carpetas:
- `%APPDATA%\...\Plugins\ClashApprover\`
- `%APPDATA%\...\Plugins\EGISStreetView\`
- `%APPDATA%\...\Plugins\EgisPropertyImporter\`
