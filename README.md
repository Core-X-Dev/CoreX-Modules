# CoreX Modules

This directory contains additional modules for the CoreX Framework. These modules extend the core functionality of CoreX and can be installed independently.

## Available Modules

### Core Modules (Built-in)
These modules are included with the CoreX Framework:

- **Multi-Character** - Multi-character system with perma-death
- **Jobs** - Comprehensive job system
- **Inventory** - Weight-based inventory system
- **Banking** - Bank account management
- **Vehicles** - Vehicle garage and ownership
- **Admin Menu** - Admin tools and management

### Community Modules
These modules are developed by the community:

*(No community modules available yet)*

## Installing Modules

### Method 1: Manual Installation
1. Download the module from the releases page
2. Extract to your `CoreX-Modules/` directory
3. Add the module to your `server.cfg`:
   ```cfg
   ensure CoreX-Modules/module-name
   ```

### Method 2: Git Installation
```bash
cd CoreX-Modules
git clone https://github.com/Core-X-Dev/CoreX-Modules.git
```

## Creating Your Own Module

### Module Structure
```
module-name/
├── fxmanifest.lua
├── config.lua
├── client/
│   └── main.lua
├── server/
│   └── main.lua
├── shared/
│   └── functions.lua
├── html/
│   ├── index.html
│   ├── style.css
│   └── script.js
└── README.md
```

### Example fxmanifest.lua
```lua
fx_version 'cerulean'
game 'gta5'

name 'CoreX Module - Example'
description 'Example module for CoreX Framework'
author 'Your Name'
version '1.0.0'

shared_scripts {
    'shared/functions.lua'
}

client_scripts {
    'client/main.lua'
}

server_scripts {
    'server/main.lua'
}

ui_page 'html/index.html'

files {
    'html/index.html',
    'html/style.css',
    'html/script.js'
}

dependencies {
    'CoreX'
}
```

### Module Guidelines
1. **Follow CoreX conventions**: Use the same coding style and patterns
2. **Use CoreX exports**: Utilize CoreX's built-in functions
3. **Include documentation**: Provide clear README and documentation
4. **Test thoroughly**: Ensure compatibility with CoreX
5. **Version properly**: Use semantic versioning

## Module Development

### Using CoreX Functions
```lua
-- Get player data
local player = exports['CoreX']:GetPlayer(source)

-- Send notification
TriggerClientEvent('corex:showNotification', source, 'Hello World!', 'success')

-- Use locale
local message = exports['CoreX']:GetLocale('module_message')

-- Database operations
exports['CoreX']:DatabaseQuery('SELECT * FROM players', {}, function(result)
    -- Handle result
end)
```

### Configuration
Create a `config.lua` file for your module:

```lua
Config = {}

Config.ModuleName = {
    enabled = true,
    debug = false,
    settings = {
        -- Your settings here
    }
}
```

### Events
Use CoreX's event system:

```lua
-- Register event
RegisterNetEvent('corex:moduleEvent')
AddEventHandler('corex:moduleEvent', function(data)
    -- Handle event
end)

-- Trigger event
TriggerEvent('corex:moduleEvent', data)
```

## Contributing

To contribute a module:

1. Fork the repository
2. Create your module in a new branch
3. Follow the module guidelines
4. Test thoroughly
5. Submit a pull request

## Support

For module development support:

- **Documentation**: [CoreX Documentation](https://docs.core-x.dev)
- **Discord**: [CoreX Discord](https://discord.gg/corex)
- **Issues**: [GitHub Issues](https://github.com/Core-X-Dev/CoreX/issues)

---

**CoreX Modules** - Extending CoreX Framework 