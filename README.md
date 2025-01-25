# Vue.js Development Environment with DDEV and PM2

This DDEV setup provides a streamlined development environment for building Vue.js applications with Node.js and PM2. The setup includes a PHP-based web environment, a MariaDB database, and integrates PM2 to manage your Vue.js development server.

## Project Setup: `vue-ddev-setup`

### Key Features:
- **PHP 8.2** web server (nginx-fpm)
- **MariaDB 10.4** database
- **Node.js 18** for Vue.js app development
- **PM2** to run and manage the Vue.js development server
- **Yarn** for package management
- **Auto-generation of Vue.js app** if no existing `yarn.lock` is found
- Automatically starts the Vue.js development server on port 3000.

### How to Use:

1. **Clone this repository** or create a new project folder.
   
2. **Install DDEV**:
   - Follow the instructions for installing DDEV from [here](https://ddev.readthedocs.io/en/stable/#installation).
   
3. **Start DDEV**:
   - Run `ddev start` in the terminal from your project folder.

4. **Vue.js App Initialization**:
   - If no `yarn.lock` file is found, the setup will automatically generate a Vue.js app using the Vue CLI.

5. **Access Your Development Server**:
   - Once DDEV has finished setting up, access your Vue.js app via `https://vue-ddev-setup.ddev.site:3000`.

### PM2 Commands:

PM2 helps manage the Vue.js development server and can also be used to monitor the application or restart it if needed. Below are some useful PM2 commands:

- **Start the app**:
  - `pm2 start "yarn dev --host"`  
    Starts the Vue.js development server and binds it to port 3000.

- **List all processes**:
  - `pm2 list`  
    Displays all the processes managed by PM2.

- **Monitor the app in real-time**:
  - `pm2 monit`  
    Opens a real-time monitor of all your applications, showing CPU and memory usage.

- **Restart the app**:
  - `pm2 restart <app_name_or_id>`  
    Restarts the Vue.js development server (replace `<app_name_or_id>` with the actual name or ID of your app, for example, `pm2 restart 0`).

- **Stop the app**:
  - `pm2 stop <app_name_or_id>`  
    Stops the running Vue.js development server.

- **Delete the app from PM2**:
  - `pm2 delete <app_name_or_id>`  
    Removes the app from PM2's process list.

- **Save the current PM2 process list**:
  - `pm2 save`  
    Saves the current list of PM2 processes, which can be restored upon system reboot.

- **Startup Script**:
  - `pm2 startup`  
    Generates a startup script to run PM2 and its processes automatically when the system reboots. This is useful for keeping the Vue.js app running after a restart.

- **View logs**:
  - `pm2 logs`  
    Displays the logs of all running PM2 processes. You can also specify a specific app to view logs for, like `pm2 logs <app_name_or_id>`.

- **Check the status of the app**:
  - `pm2 status <app_name_or_id>`  
    Provides the status of a specific app (whether it’s online, stopped, etc.).

- **Graceful restart**:
  - `pm2 reload <app_name_or_id>`  
    Restarts the application gracefully, which helps avoid downtime.

- **Clear all logs**:
  - `pm2 flush`  
    Clears all logs from PM2.

### Troubleshooting:

- If you encounter issues with starting PM2, ensure you have `yarn` installed inside the DDEV container by running `ddev ssh` and executing `yarn --version`.
- For any problems related to Vue.js, check the generated logs or run `ddev logs` to debug.
