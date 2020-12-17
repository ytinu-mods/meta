# ytinu Mod Manager Metadata

### `meta.json`

```jsonc
{
    "version": "1.2.3",
    "downloads": {
        "windows": "https://github.com/ytinu-mods/ytinu/releases/download/v1.2.3/ytinu.exe",
        "linux": "https://github.com/ytinu-mods/ytinu/releases/download/v1.2.3/ytinu",
        "macos": "https://github.com/ytinu-mods/ytinu/releases/download/v1.2.3/ytinu.app",
    },
    "messages": [
        {
            "id": "update_1.0",
            "version": "<semver constraint>",   // optional, e.g. "<1.0"
            "message": "You should update!!",   // can contain markdown or something like that
            "icon": "warning",                  // optional, defaults to "info", possible values: "info"/"warning"/"error"
            "show_always": true,                // optional, defaults to false
        }
    ],
    "games": [
        {
            "id": "Desperados3",
            "name": "Desperados III",
            "appid": "610370",
            "recommended_mods": ["ConfigurationManager"]
            // "image": "<url>",                // something to consider for the future
        }
    ],
    "mods": [ /* See <game>.json */ ]
}
```

### `games/<game>.json`

Download url can be `.dll` or `.zip` that will be placed in the `plugins` directory.

```jsonc
{
    "mods": [
        {
            "version": "1.2.3",
            "id": "ExtendedCheats",
            "name": "Extended Cheats",
            "download": "https://github.com/benediktwerner/Desperados3Mods/releases/download/cheats-v1.1.1/ExtendedCheats.dll",
            "extract_to_root": true,    // optional, if true zip mods will be extracted to the game directory instead of `plugins`
            "files": [                  // optional, used mainly for uninstallation.
                                        // if not specified all files and directories starting with `plugins/<mod id>` will be removed
                "plugins/ConfigurationManager.dll",
                "plugins/ConfigurationManager.xml",
            ],
            "dev_mod": true,            // optional, set to true if the mod is mostly intended for mod developers
            "description": "Adds more cheats",      // optional
            "ytinu_version": "<semver constraint>", // optional
            "source": "https://github.com/benediktwerner/Desperados3Mods",      // optional
            "homepage": "https://github.com/benediktwerner/Desperados3Mods",    // optional
        }
    ]
}
```

### External mod repo

```jsonc
{
    "games": [ /* See meta.json */ ],
    "mods": {
        "Desperados3": [ /* See <game>.json */ ]
    }
}
```
