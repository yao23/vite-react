# React 19 migration verification

OpenHands reported the following results for a patch reconstructed on November 22, 2026, from the original candidate and repair logs.

| Item | Recorded value |
| --- | --- |
| Base commit | `b3bd6ec9bd5db9a7cfb90c51e995463b5dae2979` |
| Exported file | `react19-reconstructed.patch` |
| SHA-256 reported for that file | `2b2e135ee9f3f0350245cc2238585beb2fd50f4e843733bf550bf7184cfea441` |
| Files in the patch | `README.md`, `package.json`, `yarn.lock` |
| Clean installation | Yarn 1.22.22, `install --frozen-lockfile`, exit 0 |
| Installed versions | react 19.3.1 and react-dom 19.3.1 |
| Build | Exit 0 |
| Tests | Exit 0, 8 files and 11 tests passed |
| Lint | Exit 0 |

The first candidate changed the manifest without updating the lockfile. The frozen install in a fresh checkout failed. During repair, the first build also exposed a missing Testing Library peer dependency, `@testing-library/dom`. OpenHands reported applying the exported patch in a second fresh checkout for the verification above. This record transcribes the run and its reported patch fingerprint.
