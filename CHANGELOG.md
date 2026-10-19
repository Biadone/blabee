# Changelog

App updates and public integration source updates are recorded separately below.
Unreleased entries are drafts; a release date and download link are added after
the app is published.

Earlier app entries were compiled from published release notes on 2026-10-19.
Dates below are GitHub publication dates, not local build dates. Historical
entries describe those versions, including their limitations; they are not the
current installation or compatibility guide. Missing build numbers are not
assumed to have been publicly released. See the [README](README.md) for the
current download and setup instructions.

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

### r85

**Released:** 2026-10-17. **App version:** 0.1.0 (build 85).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.85).

- Replaced repeated searches through card history with a per-session pending-card
  index to reduce Engine lookup work.
- Improved cleanup of selection requests left behind after a Hook response,
  which could block an update, and clarified connection recovery during updates.
- Checked selection-prompt size before registering a card or saving a choice,
  including cards with many special characters.
- Fixed late account responses re-enabling expired UI permissions.
- Hardened Claude diagnostic output handling and recovery of outdated connection
  records.

### r84

**Released:** 2026-10-17. **App version:** 0.1.0 (build 84).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.84).

- Showed the selected option's title, objective, constraints and completion
  criteria in the prompt sent to Codex, while retaining ref and Hook validation.
- Sized the decision panel to its content and enabled scrolling only when the
  content exceeded the available screen space.
- Removed Later from the choice panel and kept Skip Choices.
- Made the current selection and next action clearer during onboarding.
- Improved Codex installation-path diagnostics, installation help and connection
  guidance after a recheck.

### r83

**Released:** 2026-10-16. **App version:** 0.1.0 (build 83).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.83).

- Started long-lived connection helpers from a separately verified runtime to
  reduce new connections holding files inside the installed app bundle.
- Checked active requests and connections before updating and deferred
  replacement when a safe state could not be verified.
- Included Engine, task-delivery and connection-diagnostic hardening.

**Known limitation at release:** Existing connections were not automatically
moved to the new runtime and could still block installation. Affected apps or
background services needed to disconnect normally before retrying. Replacing
the service while retaining a Claude connection was not supported.

### r81

**Released:** 2026-10-10. **App version:** 0.1.0 (build 81).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.81).

- Made English the default app language and added a persistent Korean setting.
  Provider card text, commands and user input retained their original language.
- Added ordinary Hook one-time approval support for signature-verified Codex
  0.162.0 and 0.162.1 arm64 binaries; unregistered or modified binaries remained
  rejected.
- Fixed a wait between app termination and background-service cleanup that could
  leave the updater at "Preparing update".

**Scope at release:** The Codex addition covered ordinary Hook approval, not
full Plugin CLI, managed App Server or session restoration qualification for
those versions. An r80 updater already stuck preparing still required a manual
DMG installation.

### r80

**Released:** 2026-10-06. **App version:** 0.1.0 (build 80).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.80).

- Bounded storage-lock waits and allowed one recovery attempt after a temporary
  write failure when the original data remained available, retaining integrity,
  permission and duplicate-execution checks.
- Strengthened date/time input validation and timing checks when Hook and
  delivery records arrived in a different order.
- Included Codex 0.159.3 and 0.160.0 support and the Claude MCP/Hook connection.

**Known limitation at release:** Automatic recovery after restart was not
provided for older interrupted records whose original data had been lost.

### r75

**Released:** 2026-09-27. **App version:** 0.1.0 (build 75).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.75).

- Required Google or GitHub sign-in to use Blabee.
- Added server-managed account suspension, resumption and service-wide access
  control without forcibly terminating ongoing Codex or Claude work. Access was
  checked every 60 seconds while connected; an existing grant lasted at most
  five minutes during a connection failure.
- Shipped the combined Codex/Claude app with ordinary Claude MCP/Hook integration,
  without requiring development Channels options.

### r57

**Released:** 2026-09-17. **App version:** 0.1.0 (build 57).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.57).

- Introduced the Air UI and bee menu-bar icon, with revised card titles,
  shortcut hints and detail previews.
- Added navigation between tasks and skipping choices. Fixed older approval
  responses overwriting the current task after a new prompt or reconnection.
- Reduced unnecessary UI refreshes and improved service waiting and session
  history memory handling.
- Included optional error diagnostics, usage statistics and a feedback screen.
  Automatic reporting followed consent, expanded statistics required renewed
  consent, and feedback text could be reviewed before submission.

### r42

**Released:** 2026-09-16. **App version:** 0.1.0 (build 42).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.42).

- Added a direct Update button for an available installer, starting download and
  signature, notarization and checksum verification inside Blabee.
- Kept an explicit confirmation before closing managed work and installing the
  update. Offered the release page as a fallback when the installer was missing
  or invalid.
- Retained r41's managed Codex 0.154.0 session save/restore flow. This did not
  extend restoration to arbitrary external Codex sessions or unsent drafts.

### r41

**Released:** 2026-09-16. **App version:** 0.1.0 (build 41).
[Original release notes](https://github.com/Hyunwoojooo/biadone/releases/tag/blabee-v0.1.0%2Bbuild.41).

- Added GitHub Release downloads with signature, notarization and checksum
  verification.
- Added save, shutdown and post-update restoration for Blabee-managed Codex
  0.154.0 sessions using their exact session IDs and working folders.
- Deferred automatic shutdown while work or approval was pending, or when saving
  could not be confirmed.

**Scope at release:** Unsent drafts were not restored. The complete update
between two notarized app versions and restoration through a real terminal had
not been validated in that release work.

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
