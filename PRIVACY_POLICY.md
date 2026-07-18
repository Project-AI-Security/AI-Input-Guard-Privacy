# Privacy Policy for AI Input Guard

**Effective date:** July 18, 2026  
**Last updated:** July 18, 2026

AI Input Guard ("the Extension") helps users identify and protect credentials, secrets, personally identifiable information (PII), and other sensitive content before it is submitted to a website. This Privacy Policy explains what information the Extension processes, where processing occurs, and the choices available to users.

## Summary

- Built-in secret detection runs locally in the browser.
- The Extension does not sell personal information or use it for advertising.
- The Extension does not collect browsing history or track browsing activity.
- Draft text, raw credentials, images, and files are not retained in extension storage.
- Microsoft Presidio integrations are optional and disabled by default.
- When Presidio is enabled, checked content is sent only to the Presidio endpoint configured by the user.
- The developer does not operate a server that receives protected content from the Extension.

## Information the Extension Processes

The Extension may temporarily process the following information when the user performs a protected action:

- Text pasted into an editable website control.
- Text in a likely message or prompt field when the user attempts to submit it.
- Images or supported files selected, pasted, or dropped into a website when file protection is enabled.
- Detection results, such as the category and location of a possible credential or PII value.

This processing is necessary to warn the user and provide options to redact selected findings, allow the original content, or cancel the action.

The Extension is designed to inspect user-initiated input and transfer events. It is not designed to collect general webpage content, browsing history, passwords entered into password controls, authentication forms, or unrelated page activity.

## Local Processing

The built-in secret detector processes content locally within the user's browser. Content is held in memory only for the time needed to inspect it and complete the user's selected action. The Extension does not intentionally write raw drafts, credentials, images, or file contents to Chrome extension storage or browser logs.

Finding previews shown to the user are masked to avoid unnecessarily displaying complete sensitive values.

## Optional Microsoft Presidio Processing

The Extension can optionally connect to Microsoft Presidio Analyzer, Anonymizer, and Image Redactor services. These features are disabled by default and must be enabled and configured by the user.

When enabled:

- Text being checked may be sent to the configured Presidio Analyzer endpoint.
- Text selected for anonymization may be sent to the configured Presidio Anonymizer endpoint.
- Images selected for protection may be sent to the configured Presidio Image Redactor endpoint.
- Supported text-like file contents may be sent to the configured Analyzer or Anonymizer endpoint when the relevant protection is enabled.

The default endpoints use the local loopback address (`127.0.0.1`) so processing can occur on the user's own device. Users may configure a remote endpoint. Non-local endpoints must use HTTPS.

AI Input Guard does not control a Presidio service configured by the user. If a user chooses a remote or third-party endpoint, that service's operator may receive and process the submitted content under its own privacy and retention practices. Users are responsible for confirming that a configured endpoint is trusted and appropriate for their data.

## Information Stored Locally

The Extension uses `chrome.storage.local` to store information needed to provide its functionality, including:

- Whether the Extension and individual protection features are enabled.
- User-created keyword or regular-expression protection rules.
- Presidio endpoint addresses and related configuration.
- Selected Presidio entity types, language, score threshold, file-size limit, and failure policy.
- Aggregate local counters, such as the number of scans, warnings, and blocked actions.
- Remembered exceptions created when a user chooses to allow a specific detected input.

Remembered exceptions contain fingerprints, classification labels, and masked previews. They do not contain the original raw sensitive value. An exception applies only to the same complete input unless the user removes it.

This information remains on the user's device until it is changed, reset, removed through the Extension's settings, or deleted when the Extension is uninstalled according to the browser's extension-data behavior.

## Information the Extension Does Not Collect

The Extension does not intentionally collect or retain:

- Browsing history.
- Website visit records.
- Advertising identifiers.
- Analytics or telemetry sent to the developer.
- Complete drafts or messages.
- Raw credentials, secrets, or PII values.
- Original images or file contents.
- Account passwords entered into password fields.

## Data Sharing and Sale

The developer does not sell, rent, or trade user information. The Extension does not share protected content with advertisers, analytics providers, data brokers, or the developer.

Content is transmitted only when required for an optional Presidio feature enabled by the user, and only to the endpoint selected by that user. The Extension also retrieves ordinary resources required by websites and Chrome as part of normal browser operation, but it does not send protected content to those services on behalf of the developer.

## Permissions

### Storage

The `storage` permission is used to save protection preferences, custom rules, Presidio configuration, local aggregate counters, and privacy-preserving remembered exceptions.

### Website Access

The Extension requests access to HTTP and HTTPS websites so it can protect user-initiated input across websites, including content inside permitted frames. This access allows the Extension to observe relevant paste, submit, file-selection, and drag-and-drop events and display a review dialog before sensitive content is transferred.

Website access is also required to connect to optional user-configured Presidio endpoints. Broad host access is not used to collect browsing history or monitor unrelated browsing behavior.

## Data Security

The Extension uses local processing by default, masks displayed findings, avoids storing raw protected content, rejects non-local Presidio endpoints that use unencrypted HTTP, and supports fail-closed behavior when configured protection services are unavailable.

No software can guarantee that every sensitive value will be detected. Users should review content before submitting it and should not rely on the Extension as the only control protecting high-risk or regulated information.

## User Choices

Users can:

- Turn the Extension or individual protection features on or off.
- Keep all processing local by leaving Presidio disabled or using local Presidio endpoints.
- Configure or remove custom protection rules.
- Review and delete remembered exceptions.
- Reset locally stored statistics.
- Cancel a protected action instead of transmitting content.
- Uninstall the Extension at any time.

## Children's Privacy

The Extension is not directed to children under 13 and is intended as a security and privacy tool for general and professional use. The developer does not knowingly collect personal information from children.

## Changes to This Policy

This Privacy Policy may be updated when the Extension's functionality or data practices change. The updated policy will include a revised "Last updated" date. Material changes will be reflected in the published policy and, when appropriate, in the Extension's release information.

## Contact

For questions, privacy requests, or concerns about this policy, contact the developer through the support contact provided on the AI Input Guard Chrome Web Store listing or through the project's official support page.

