# Changelog

App updates and public integration source updates are recorded separately below.
Unreleased entries are drafts; a release date and download link are added after
the app is published.

## App updates

### r86

**Released:** 2026-10-19. **App version:** 0.1.0 (build 86).
Developer ID signed and Apple notarized.
[Download r86](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.86).

#### Improved

- First-run Settings identifies service or local storage problems that block
  setup and shows the relevant recovery action.
- Connection guidance distinguishes tools that are ready to connect from tools
  that need attention. An incomplete Claude setup no longer hides the next
  available Codex connection action.
- Service guidance offers an enable action for a disabled service and a separate
  step to remove an outdated service registration before restarting.

#### Fixed

- Choosing Connect can restore a missing Claude auto-connect launcher when the
  existing terminal entry is verified as Blabee-managed. Modified or conflicting
  entries still require review.

**Recovery note:** Starting fresh with local storage requires confirmation and
does not restore lost selection history. Installing this update does not
automatically reset storage.

## Integration source updates

### Initial public integration snapshot — 2026-10-18

- Published selected Codex plugin and current Claude MCP/Hook client sources.
- Added frozen v1 contracts, synthetic fixtures and isolated regression tests.
- Added English and Korean product/setup documentation and offline examples.
- Kept the macOS app, Swift Engine and operational backend outside this source
  scope. At the time of this source snapshot, the app download was the signed
  and notarized r85 release.

The integration snapshot remains r85; its version and the app build number are
separate. See
`PUBLIC_SOURCES.json` for the exact published file inventory.
