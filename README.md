# Triple A Studios - Utils
A custom unity package that contains utilities for unity projects ranging from <b>Extension Methods</b> to <b>Timer</b>,
etc.

___

## Installation
### Method 1 (Recommended):
Using Git Url:
1. Copy the git URL.
2. Open the package manager window in your unity project.
3. Click on the little "+" icon in the top left corner and from the dropdown, select "Add package from git URL".
4. Paste the URL, click "Add" button.

### Method 2:
By Unity Package:
1. Download the .unitypackage file from the [Release Page](https://github.com/Triple-A-Studios/TripleA-Utils/releases 
"Releases") or from the [itch page](https://aliqadir.itch.io/utils "Itch Link").
2. Import the package into your unity project.

### Method 3 (Not Recommended):
Cloning the git repository directly(gives access unreleased features and access to the branches in development)
1. Copy the git URL.
2. Clone the repository directly into your project.

___

## API Reference

Full documentation website coming soon. Quick reference below to get started — namespace is `TripleA.Utils.*`.

### Extensions (`TripleA.Utils.Extensions`)

Import with `using TripleA.Utils.Extensions;`, then call as normal extension methods.

| Type | Examples |
|---|---|
| `string` | `str.IsBlank()`, `str.OrEmpty()`, `str.Shorten(20)`, `str.Slice(2, -1)` |
| `int` / `float` / `double` | `5.IsEven()`, `a.AtLeast(0)`, `a.AtMost(100)`, `part.PercentageOf(whole)` |
| `Vector2` / `Vector3` | `v.With(x: 1)`, `v.Add(y: 2)`, `v.Clamp(0, 1)`, `v.Round()`, `v3.ToVector2IgnoreZ()` |
| `Color` | `color.WithAlpha(0.5f)`, `color.With(r: 1)` |
| `GameObject` | `go.GetOrAddComponent<T>()`, `go.DestroyChildren()`, `go.HideInHierarchy()` |
| `Transform` | `t.Children()`, `t.Reset()`, `t.InRangeOf(target, 10f)`, `t.DestroyChildren()` |
| `List<T>` / `IList<T>` | `list.Shuffle()`, `list.Swap(0, 1)`, `list.RefreshWith(newItems)` |
| `IEnumerable` | `enumerable.CountEnumerable()` |

Static (non-extension) helpers: `MathExtensions.Approximately`, `MathfExtension.Max/Min`, `Vector2Math`/`Vector3Math` (dot/angle/projection helpers), `PrefabExtensions.IsUninstantiatedPrefab`.

### Observables (`TripleA.Utils.Observables`)

```csharp
using TripleA.Utils.Observables.Primaries;

ObservableInt health = new(100);
health.AddListener(newValue => Debug.Log($"Health changed to {newValue}"));
health.Value = 80; // fires the listener
```

Also available: `ObservableFloat`, `ObservableBool`, and generic `Observable<T>` for any serializable type. `TripleA.Utils.Observables.Collections` has `ObservableStack<T>` / `ObservableQueue<T>`, which raise `CollectionChanged` on push/pop/enqueue/dequeue.

### Singletons (`TripleA.Utils.Singletons`)

```csharp
public class GameManager : PersistentSingleton<GameManager> { }

GameManager.Instance.DoSomething();
```

- `GenericSingleton<T>` — lazy, auto-creates a GameObject if none exists in the scene.
- `PersistentSingleton<T>` — same as above, plus `DontDestroyOnLoad`.
- `RegulatorSingleton<T>` — enforces a single instance across scene loads by destroying duplicates.

___

## Change Log

View Changelog [here](CHANGELOG.md).

___

## Issues

No known issues as of 16 Mar 2025.

___

## Future updates

Upcoming updates (as of 13 Jan 2025): 
- Create a Subsystem in player loop to manage data binding to the timers to reduce unnecessary overhead created by 
actions to update time ticks.

___

## Contributing guidelines:

If you wish to contribute to the project, please follow the general contribution guidelines as outlined below:

-   Fork the repository and create a branch from the main branch
-   Make your contributions and commit your changes to your branch
-   Submit a pull request detailing the changes made
-   Wait for your changes to be reviewed and merged

___

## License information

This project is licensed under the MIT license, which can be found on the GitHub repository. The MIT license allows for 
the use, modification, and distribution of the code for both commercial and non-commercial purposes.

___

## Contact information

For any bug reports, issues, or help regarding the setup of the project, please feel free to contact me on 
[LinkedIn](https://www.linkedin.com/in/ali--qadir/ "LinkedIn Profile"), 
Instagram [@oily.oli](https://www.instagram.com/oily.oli/ "Insta @oily.oli"), or mail me at 
[ali.qadir.007@outlook.com](mailto:ali.qadir.007@outlook.com?subject=[GitHub]%20Dynamic%20Character%20Controller%20Issue "Mail to Ali Qadir"). 
My contact information can be found on my GitHub profile also.
Alternatively you can leave comments on my [itch page](https://aliqadir.itch.io/utils "Itch Link") too.
