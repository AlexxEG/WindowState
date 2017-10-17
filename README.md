# WindowState
Library to help save window state of WinForms windows. It will store `Size`, `Location`, `FormWindowState` (Normal, Minimized, Maximized), `ColumnHeader.Width` and `SplitContainer.Distance`. [`WindowStates`](WindowState/WindowStates.cs) can be put directly into settings.

# Usage

### Initialization
Anyway, initialize a `WindowStates` object somewhere. Can be put directly into `Properties.Settings.Default`, it will serialize automatically:

```csharp
var settings = Properties.Settings.Default;

// Initialize WindowStates collection if null
if (settings.WindowStates == null)
{
    settings.WindowStates = new WindowStates();
}
```

### Load
Use the [```WindowStates.Load(Form, throwErrorIfNotFound, restoreColumns = true, restoreSplitContainers = true)```](WindowState/WindowStates.cs#L100) function:

```csharp
settings.WindowStates.Restore(this, false);
```

### Save
Use the [```WindowStates.Save(Form, saveColumns = true, saveSplitContainers = true)```](WindowState/WindowStates.cs#L119) function:

```csharp
settings.WindowStates.Save(this);
```
