# Rush npmrc repro

This demonstrates a rush managed repository not using the correct .npmrc configuration when rush commands are invoked via npm scripts.

## Steps to reproduce

1. Clone the project

```bash
git clone https://github.com/a-b-r-o-w-n/rush-npmrc-repro.git
cd rush-npmrc-repro
```

2. Run `rush update` directly

```bash
node common/scripts/install-run-rush.js update
```

This command should fail because the registry `https://fooregistry.npmjs.org` does not exist.

3. Run `rush update` via npm script

```bash
npm run update
```

This command succeeds despite having a bogus registry in the npmrc.
