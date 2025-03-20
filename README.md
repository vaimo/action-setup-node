# GitHub Action For Node Setup

This action installs Node.js and optionally configures access to a custom NPM registry.

# Supported versions
- v1
    - Installs the specified Node.js version.
    - Optionally configures authentication for a private/custom NPM registry.

# Usage

```yaml
- name: Setup node
  uses: vaimo/setup-node@v1
  with:
    # Node.js version to install (Required)
    node-version: ${{ inputs.node-version }}

    # Working directory for the action (Optional, defaults to root)
    working-directory: src
    
    # Enable or disable custom NPM registry access (Optional, defaults to false)
    enable-npm-registry: ${{ inputs.enable-npm-registry }}

    # Custom NPM registry URL (e.g., https://registry.npmjs.org or private registry)
    npm-registry-url: ${{ secrets.npm-registry-url }}

    # NPM package scope (e.g., @yourcompany) (Required if enable-npm-registry is true)
    npm-registry-scope: ${{ secrets.npm-registry-scope }}

    # Authentication details (Required if enable-npm-registry is true)
    npm-registry-email: ${{ secrets.npm-registry-email }}
    npm-registry-user: ${{ secrets.npm-registry-user }}
    npm-registry-password: ${{ secrets.npm-registry-password }}
```

