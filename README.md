# hugo-mock-landing-page-domain-name

This repository is a demonstration of how to automate the deployment of a Hugo website to GitHub Pages using GitHub Actions. The process involves setting up a workflow that builds the website and deploys it to the `gh-pages` branch whenever changes are pushed to the main branch.

## Workflow Explanation

The GitHub Actions workflow, defined in `.github/workflows/gh-pages-deployment.yaml`, automates the deployment of the Hugo website. Here's a brief overview of what each section of the workflow does:

- **Trigger:** The workflow is triggered on a push to the `main` branch, ensuring that updates are automatically deployed.
- **Environment:** It runs on an Ubuntu 22.04 environment, providing a stable and consistent build platform.
- **Steps:**
  - **Check Out Source Repository:** Uses `actions/checkout@v3.5.1` to clone the repository, ensuring that Hugo themes and the full history needed for `.GitInfo` and `.Lastmod` are available.
  - **Initialize Hugo Environment:** Sets up Hugo using `peaceiris/actions-hugo@v2.6.0`, specifying the Hugo version and enabling extended features.
  - **Compile Hugo Static Files:** Builds the website with draft pages included, performs cleanup, and minifies the output for optimal performance.
  - **Publish to GitHub Pages:** Uses `peaceiris/actions-gh-pages@v3.9.3` to deploy the site to the `gh-pages` branch, with actions authenticated via the `GITHUB_TOKEN`. Also notes the possibility of using a custom domain.

## Customization and Usage

You are encouraged to fork or import this repository to experiment with your own Hugo website deployment. Adjust the `config.toml` file's baseURL to match your repository and follow the detailed guide for each step to ensure a smooth setup.


