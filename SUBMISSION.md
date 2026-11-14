# Marketplace submission

Issue title: **[Plugin]: omaxrs**

The draft issue body is [docs/marketplace-submission.md](docs/marketplace-submission.md). Its category is `System`, with tags `bar`, `vpn`, and `quickshell`. The widget category `Network` in the manifest is a separate bar-host category.

## Preview and logo assets

Following the [official submission requirements](https://github.com/omacom/omarchy-plugin-marketplace/blob/main/SUBMISSION.md#check-the-repository):

- Keep the banner with the logo and UI screenshot at repository-root `preview.png`, beside `manifest.json`. The marketplace discovers it automatically; no manifest entry is needed. The original screenshot is preserved separately at `docs/images/panel.png`.
- Keep only one marketplace preview. Supported names are `preview.png`, `preview.jpg`, `preview.jpeg`, `preview.webp`, and `preview.avif`.
- The marketplace strips metadata and generates optimized card and detail images. Inputs must not exceed 50 MB or 40 megapixels; normal screenshots need no manual resizing or compression.

The shared xrs/omaxrs logo is `logo.png`, referenced by the README. The current marketplace has no separate logo discovery convention, and the Omarchy manifest reference defines no logo field. It is not the marketplace preview and does not configure the runtime bar icon.

## Submission steps

Before submitting:

1. Run `omarchy plugin validate .` and complete the desktop checks in the README on the version being published.
2. Review the marketplace banner in root `preview.png` before publishing. Do not include subscription URLs, credentials, or private server details.
3. Commit and push the prepared version to the public repository. Marketplace validation reads the public repository, not this checkout.
4. Recheck that `io.github.mahdjalili.omaxrs` is available. It was absent from the marketplace registry during preparation; IDs are permanent and availability is not reserved.
5. Review the draft body, confirm all five checklist statements, and change the checkboxes to `[x]` only when true. Ownership and permission must be confirmed by the owner.
6. Submit through the [issue form](https://github.com/omacom/omarchy-plugin-marketplace/issues/new?template=submit-plugin.yml), or create an issue using the reviewed body:

```bash
gh issue create \
  --repo omacom/omarchy-plugin-marketplace \
  --title "[Plugin]: omaxrs" \
  --body-file docs/marketplace-submission.md
```

Do not run this command with unchecked checklist items. When an agent submits on your behalf, review the completed title and body and explicitly approve issue creation first.

Follow validation feedback in the same submission issue. Fix the repository or issue and edit the issue to trigger validation again rather than opening duplicates. Publication requires maintainer approval.

References: [publishing guide](https://plugins.omarchy.org/publish.html), [submission requirements](https://github.com/omacom/omarchy-plugin-marketplace/blob/main/SUBMISSION.md), [shell reference](https://github.com/basecamp/omarchy/blob/quattro/docs/omarchy-shell.md).
