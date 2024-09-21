---
related:
   cheat-sheet: ['Node.js']
---

## Commands

    npm list            # Show packages in local path
    npm list -g         # Show global packages
    npm list -g -p      # Show global packages, parseable list

    npm view <package>

    npm install   <package>[@<version>]                # Install as prod dependency
    npm install   <package>[@<version>] --save-dev     # Install as dev dependency
    npm install   <package>[@<version>] --save-bundle  # Install as bundle dependency
    
    npm uninstall <package>[@<version>]
    npm rm <package>

    npm search <something>

    npm link   <package> # Link global package into user env
    npm unlink <package>

    npm link             # Link package into global env (when in package dir)
    npm unlink

## Security

    npm audit            # Show all vulnerable packages
    npm audit fix        # Try to upgrade vulnerable packages

    npm outdated         # Show all packages that can be updated

## Development

    npm init             # Create new package
    npm login            # Login to npmjs.com registry

    npm publish
    npm unpublish <package>

    npm adduser

    npm owner add <user> <package>
    npm owner rm  <user> <package>
    npm owner ls <package>

    npm start            # Start an app

## Alternative registries

Scoped login to alternative registry

    npm login --scope=@NAMESPACE --auth-type=legacy --registry=https://npm.pkg.github.com

Set publish target in `package.json`

    "publishConfig": {
        "registry": "https://npm.pkg.github.com"
    },

## Using npm modules for clients

E.g. exposing jquery with Express:

    app.use('/assets', [
        express.static(path.join(__dirname, 'node_modules', 'jquery', 'dist'))
    ]);

which allows the client to fetch `/assets/jquery.js`.

## Configure a private registry

    cat <<EOF > /etc/npmrc
    registry=${PRIVATE_REGISTRY_URL}
    _auth = $(echo -n "${username}:${password}"| base64 -w0)
    email = contact@example.com
    always-auth = true
    EOF

## Misc

-   [NPM global vs locally installed modules](http://blog.nodejs.org/2011/03/23/npm-1-0-global-vs-local-installation/)
