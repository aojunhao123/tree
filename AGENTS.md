# AGENTS.md

## Cursor Cloud specific instructions

This is `rc-tree` (`@rc-component/tree`), a React Tree UI component library from the Ant Design ecosystem. It is a pure frontend library with no backend or database dependencies.

### Quick reference

| Task         | Command                         |
| ------------ | ------------------------------- |
| Install deps | `npm install`                   |
| Lint         | `npm run lint`                  |
| Test         | `npm test`                      |
| Build        | `npm run compile`               |
| Dev server   | `npm start` (dumi on port 8000) |
| Coverage     | `npm run coverage`              |

### Non-obvious caveats

- **No lockfile**: All lockfiles (`package-lock.json`, `yarn.lock`, `pnpm-lock.yaml`) are `.gitignore`d. `npm install` resolves fresh each time — expect deprecation warnings but no failures.
- **`.npmrc`**: Contains `node-options="--openssl-legacy-provider"` which is needed for compatibility with webpack tooling under Node 17+. Do not remove it.
- **dumi port**: The dev server (`npm start`) runs on **port 8000** (not 9001 as the README states). Navigate to `http://localhost:8000/demo/basic` for interactive demos.
- **Test console warnings**: Tests produce React `act(...)` warnings in console output — these are expected and do not indicate test failures. All 212 tests should pass.
- **Husky**: `npm install` triggers the `prepare` script which sets up husky git hooks. The pre-commit hook runs `lint-staged` (prettier formatting).
