# Unraid Templates for Community Applications

Unraid Community Applications (CA) templates for self-hosted and homelab services: Docker templates (XML) plus a CA plugin template, maintained by [@masterwishx](https://github.com/masterwishx).

## Table of Contents

- [Installation](#installation)
- [Available Templates](#available-templates)
- [Plugins](#plugins)
- [Notes](#notes)
- [Repository Structure](#repository-structure)
- [Contributing](#contributing)
- [Support](#support)

## Installation

### Via Community Applications

Most templates can be found by searching for the app name in the **Apps** tab.

### Manually (Template Repository)

1. Open the **Docker** tab in the Unraid WebGUI.
2. Scroll down and click **Add Container**.
3. In the **Template** dropdown, pick the template you want (it will appear after step 4 below), or use the repository URL directly:
   - Go to **Settings → Docker** (or the **Docker** tab → *Template repositories*, in advanced view).
   - Add this URL to the **Template repositories** list and click **Save**:

     ```
     https://github.com/masterwishx/unraid-templates
     ```
4. Go back to **Docker → Add Container**, choose the template from the **User templates** list, adjust the settings and click **Apply**.

## Available Templates

| Template | Description | Upstream |
| --- | --- | --- |
| [`FileBrowserQuantum.xml`](FileBrowserQuantum.xml) | Modern, responsive web file manager with user management, sharing, and file preview/editing. | [gtsteffaniak/filebrowser](https://github.com/gtsteffaniak/filebrowser) |
| [`browserless.xml`](browserless.xml) | Headless Chrome as a service (Puppeteer, Playwright, Selenium, REST APIs). Used as the Playwright content fetcher for changedetection.io. | [browserless/browserless](https://github.com/browserless/browserless) |
| [`browserless-v2.xml`](browserless-v2.xml) | Browserless v2 template. | [browserless/browserless](https://github.com/browserless/browserless) |
| [`UrBackup.xml`](UrBackup.xml) | Open-source client/server backup system with image and file backups, running without interrupting the system. | [uroni/urbackup_backend](https://github.com/uroni/urbackup_backend) |
| [`GrafanaMimir.xml`](GrafanaMimir.xml) | Horizontally scalable, highly available, multi-tenant long-term storage for Prometheus. | [grafana/mimir](https://github.com/grafana/mimir) |
| [`Fio-Tester.xml`](Fio-Tester.xml) | Flexible I/O Tester for simulating and benchmarking storage workloads. | [axboe/fio](https://github.com/axboe/fio) |
| [`RedisInsight.xml`](RedisInsight.xml) | GUI for visualizing and optimizing Redis data. | [redis.io/insight](https://redis.io/insight/) |
| [`semaphore.xml`](semaphore.xml) | Modern web UI for Ansible: run playbooks, schedules, notifications, access control. | [semaphoreui.com](https://semaphoreui.com) |
| [`NetAlertX.xml`](NetAlertX.xml) | Network scanner and presence/intruder alerting. | [jokob-sk/NetAlertX](https://github.com/jokob-sk/NetAlertX) |
| [`Forgejo.xml`](Forgejo.xml) | Self-hosted Git forge (lightweight, community-driven fork of Gitea). | [forgejo.org](https://forgejo.org) |
| [`gitea-mirror.xml`](gitea-mirror.xml) | Automatically mirrors GitHub repositories to a self-hosted Gitea/Forgejo instance. | [RayLabsHQ/gitea-mirror](https://github.com/RayLabsHQ/gitea-mirror) |
| [`wikijs3.xml`](wikijs3.xml) | Wiki.js 3 (official image) with PostgreSQL setup instructions. | [requarks/wiki](https://github.com/requarks/wiki) |
| [`ci-image-gitea.xml`](ci-image-gitea.xml) | CI runner image for Gitea Actions. | [gitea/runner-images](https://gitea.com/gitea/runner-images) |
| [`ci-image-ubuntu.xml`](ci-image-ubuntu.xml) | Ubuntu-based CI runner image for Gitea/Forgejo Actions. | [catthehacker/docker_images](https://github.com/catthehacker/docker_images) |
| [`ci-image-ubuntu-24.04.xml`](ci-image-ubuntu-24.04.xml) | Ubuntu 24.04 based CI runner image for Gitea/Forgejo Actions. | [catthehacker/docker_images](https://github.com/catthehacker/docker_images) |

## Plugins

### Mover Tuning (`ca.mover.tuning.xml`)

A plugin that lets you fine-tune how the Unraid [mover](https://docs.unraid.net/unraid-os/manual/additional-settings/#mover) works.

- On scheduled runs, only move files when the cache is getting full (selectable thresholds) and/or based on file age, size, etc.
- Optionally skip the mover while a parity check/rebuild is in progress.
- Optionally validate input filenames to prevent filename-based attacks.
- Optionally disable scheduled mover runs completely.
- Manual runs ("Move Now" or `mover start`) can follow the schedule rules and/or always move everything.
- Many additional options and settings.

Links:

- Source: [masterwishx/ca.mover.tuning](https://github.com/masterwishx/ca.mover.tuning)
- Support thread: [Unraid Forums](https://forums.unraid.net/topic/70783-plugin-mover-tuning)

## Notes

### browserless + changedetection.io

To use `browserless` as the Playwright content fetcher, add this variable to your changedetection.io container after installing:

```
PLAYWRIGHT_DRIVER_URL=ws://yourIP:yourPORT/?stealth=1&--disable-web-security=true
```

More info: [changedetection.io Playwright content fetcher](https://github.com/dgtlmoon/changedetection.io/wiki/Playwright-content-fetcher) and the [Browserless Docker quickstart](https://docs.browserless.io/docs/docker-quickstart.html). The v1 image is about 910 MB.

## Repository Structure

```
.
├── configs/            # Extra config files used by templates
├── images/             # Template icons
├── ca_profile.xml      # CA author profile
├── *.xml               # Docker / plugin templates
└── README.md
```

## Contributing

Issues and pull requests are welcome.

- Found a broken template or outdated default? [Open an issue](https://github.com/masterwishx/unraid-templates/issues).
- Want to add or improve a template? Fork the repo, make your changes, and open a pull request.
- Please validate XML before submitting and keep `<Support>`, `<Project>`, and `<Icon>` links up to date.

## Support

For app-specific problems, please use the upstream project's issue tracker (see the table above). For template problems (wrong paths, ports, variables, descriptions), open an issue in this repository.

## Disclaimer

These templates are provided as-is, without warranty. The applications are developed by their respective authors; this repository only provides Unraid templates for running them.
