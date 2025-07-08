# My studio in 3D

## Links

- [GitHub](https://github.com/Aashu3739/studio-in-3d)

![Project Preview](assets/studio.png)

## Setup

Download [Node.js](https://nodejs.org/en/download/).
Run this followed commands:

``` bash
# Install dependencies (only the first time)
npm install

# Run the local server at localhost:8080
npm run dev

# Build for production in the dist/ directory
npm run build
```

## Troubleshooting

### Node.js v17+ / v18+ / v22+ OpenSSL Error
If you see an error like:

```
Error: error:0308010C:digital envelope routines::unsupported
```

Webpack 4/5 and many tools are not fully compatible with OpenSSL 3 defaults in Node.js 17 and above.

**Workaround:**

For Windows PowerShell:
```powershell
$env:NODE_OPTIONS="--openssl-legacy-provider"
npm run dev
# or for production build
npm run build
```
For Windows CMD:
```cmd
set NODE_OPTIONS=--openssl-legacy-provider
npm run dev
npm run build
```

**Recommended:** Use Node.js v16 (LTS) for best compatibility.

---

### Dependency Issues or Version Mismatch
If you see errors about webpack, webpack-cli, or webpack-dev-server versions, or about unknown properties in the devServer config:

1. Remove all installed modules and lock file:
   ```powershell
   Remove-Item -Recurse -Force node_modules; Remove-Item -Force package-lock.json
   ```
2. Reinstall compatible versions:
   ```powershell
   npm install webpack@5.42.1 webpack-cli@4.7.2 webpack-dev-server@4.0.0 --save-dev
   npm install
   ```

---
