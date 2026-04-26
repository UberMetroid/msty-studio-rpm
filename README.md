# UberMetroid: Msty Studio RPM Builder

This repository contains an automated GitHub Actions pipeline to convert Msty Studio `.deb` packages into Fedora-compatible `.rpm` packages using FPM.

## How to build an RPM

1. Go to the **Actions** tab in this repository.
2. Select the **Build Msty Studio RPM** workflow on the left.
3. Click **Run workflow**.
4. Enter the desired version (e.g., `2.6.4`) and the direct download URL for the Ubuntu `.deb` package from the [Msty Download Page](https://msty.ai).
5. Once the workflow finishes, the `.rpm` file will be available to download as an Artifact at the bottom of the workflow summary.

## Setting up Fedora Copr (Optional)

If you want to automatically host the resulting RPMs in a Fedora Copr repository:

1. Create a project on [Fedora Copr](https://copr.fedorainfracloud.org/).
2. Go to your Copr API settings and get your API keys.
3. In this GitHub repository, go to **Settings > Secrets and variables > Actions**.
4. Add the following secrets:
   - `COPR_LOGIN`
   - `COPR_USERNAME`
   - `COPR_TOKEN`
5. Uncomment the final steps in `.github/workflows/build-rpm.yml` to enable pushing to Copr.
