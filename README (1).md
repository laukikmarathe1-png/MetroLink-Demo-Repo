# CI/CD Demo Repo

This repository is a minimal setup to help you complete **User Story 1 – CI/CD Setup Using Azure DevOps**.

## What’s included
- `azure-pipelines.yml`: A simple Azure DevOps pipeline definition.
- `scripts/validate.sh`: A basic validation script that prints environment details and exits successfully.

## How to use this repo

### 1) Create/Upload to GitHub
1. Sign in to [GitHub](https://github.com/) and create a **public** repository (e.g., `ci-cd-demo`).
2. Upload these files to the repo (keep the same structure):
   ```
   /
   ├─ azure-pipelines.yml
   └─ scripts/
      └─ validate.sh
   ```

### 2) Set up Azure DevOps pipeline
1. Go to [Azure DevOps](https://dev.azure.com/), create a project (e.g., `ci-cd-demo`).
2. Navigate to **Pipelines** → **Create Pipeline**.
3. Choose **GitHub** as the source and select your repository.
4. Pick **Existing Azure Pipelines YAML file** and point to `/azure-pipelines.yml`.
5. Click **Run**. The pipeline should fetch the code and run the validation script.

### 3) What screenshots to capture
- **Project Overview** page in Azure DevOps.
- **Pipeline run result** showing **Succeeded**.
- **Pipeline YAML view** or **Steps view** with logs.

## Files explained

### `azure-pipelines.yml`
- Uses an **Ubuntu** build agent.
- Triggers on pushes to the default branch (`main` by default).
- Runs two steps:
  1. List repository files (basic check that code is available).
  2. Execute `scripts/validate.sh`.

### `scripts/validate.sh`
- Prints environment information.
- Ensures the script is executable and exits with success.

## Troubleshooting
- If your default branch is `master`, update `trigger` in `azure-pipelines.yml` accordingly.
- Ensure `validate.sh` has Unix line endings (LF) if you’re on Windows.
- If the script isn’t executable, the pipeline includes `chmod +x` to fix it.

---

**Good luck!** This setup is intentionally minimal to meet all requirements of User Story 1.
