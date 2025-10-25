# GitHub Actions Workflow for Building DVR-Scan Installer

This directory contains the GitHub Actions workflow for building the DVR-Scan Windows installer.

## Workflow: build-installer.yml

The workflow will:
1. Run on Windows latest
2. Install Python and required dependencies
3. Build the one-file executable with PyInstaller (including LICENSE files)
4. Install NSIS via chocolatey
5. Build the NSIS installer
6. Upload the installer as an artifact

## How to use

1. Push this workflow to your repository:
   ```bash
   git add .github/
   git commit -m "Add GitHub Actions workflow for NSIS installer build"
   git push
   ```

2. Go to your repository on GitHub.com and:
   - Click "Actions" tab
   - Select "Build NSIS Installer" workflow
   - Click "Run workflow" button
   - Wait for completion (~5-10 minutes)

3. After the workflow completes:
   - Go to the completed workflow run
   - Click on "Artifacts"
   - Download "DVR-Scan-installer"
   - Extract the ZIP to get `DVR-Scan-setup-unsigned.exe`

The workflow will also run automatically when changes are pushed to:
- `installer/**` (installer files)
- `dvr_scan/**` (source code)
- `DVR-Scan.spec` (PyInstaller spec)
- The workflow file itself