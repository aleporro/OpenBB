## Running OpenBB Platform Locally (Windows)

This is a minimal, personal checklist for running the REST API again later.

### One‑time setup (already done)

- **Install Python 3.14**
  - Installed at `C:\Users\Alessandro\AppData\Local\Programs\Python\Python314\python.exe`.
- **Install project in editable mode**
  - From `D:\source\repos\Bluerabbit\OpenBB\OpenBB\openbb_platform`:
    - Run:
      ```powershell
      python dev_install.py -e
      ```
    - The script automatically detects that global Python 3.9 is not supported and uses Python 3.14.3 instead.

You only need to repeat the dev install if dependencies or your environment change significantly.

### Every time you want to run the API

1. **Open PowerShell**
2. **Go to the `openbb_platform` folder**
   ```powershell
   cd D:\source\repos\Bluerabbit\OpenBB\OpenBB\openbb_platform
   ```
3. **Start the REST API using Poetry’s environment**
   ```powershell
   poetry run uvicorn openbb_core.api.rest_api:app --host 0.0.0.0 --port 8000 --reload
   ```
   - Poetry will:
     - Detect that Python 3.9 is not supported.
     - Automatically use `python.exe (3.14.3)` for the environment.

4. **Open the docs in your browser**
   - Swagger UI: `http://localhost:8000/docs`
   - ReDoc: `http://localhost:8000/redoc`

5. **Stop the server**
   - In the same PowerShell window, press **Ctrl + C**.

