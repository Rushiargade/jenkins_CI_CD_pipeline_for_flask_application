# Pipeline Stages Description

## 1. Checkout
- Jenkins pulls the source code from the GitHub repository using SCM.

## 2. Build
- A Python virtual environment is created.
- Required dependencies are installed using pip and requirements.txt.

## 3. Test
- Unit tests are executed using pytest.
- The pipeline fails if tests do not pass.

## 4. Deploy
- The Flask application is deployed to a staging environment.
- Deployment occurs only after successful build and test stages.
