# WindowState
Library to help save window state of WinForms windows. It will store Size, Location, FormWindowState (Normal, Minimized, Maximized), ColumnHeader.Width and SplitContainer.Distance. [`WindowStates`](WindowState/WindowStates.cs) can be put directly into settings.

# Usage

### Load
Requires a bit more code then I would like atm. I wanna improve this.

Anyway, initialize a `WindowStates` collection and add a `Form`:

```csharp
var settings = Properties.Settings.Default;

// Initialize WindowStates collection if null
if (settings.WindowStates == null)
{
    settings.WindowStates = new WindowStates();
}

// Add WindowState for form if WindowStates doesn't have a entry for it
if (!settings.WindowStates.Contains(this.Name))
{
    settings.WindowStates.Add(this.Name);
}
```

Now we can restore window state like this:

```csharp
settings.WindowStates[this.Name].RestoreForm(this);
```

### Save
Simply:

```csharp
settings.WindowStates[this.Name].SaveForm(this);
```

[`RestoreForm()`](WindowState/WindowState.cs#L69) & [`SaveForm()`](WindowState/WindowState.cs#L95) have a second parameter for saving colum widths. Defaults to `true`.
