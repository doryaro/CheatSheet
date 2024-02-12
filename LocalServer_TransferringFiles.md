# Transferring Files and Directories with a Local Server

To transfer files using a local server, follow these steps:

1. **open cmd**: in the file's path

2. **Start a Local Server**: Run `python -m http.server 80`
   - Explanation:
     - `python`: Invokes the Python interpreter.
     - `-m`: Specifies that you want to run a Python module.
     - `http.server`: Specifies the name of the module you want to run. This module provides a simple HTTP server.
     - `80`: Specifies the port number on which the HTTP server should listen. Port 80 is the default for HTTP traffic.

3. **Access the Server**:
   - On another machine, open a web browser.
   - In the browser's address bar, enter the IP address of the first machine.

4. **Transfer Files**:
   - Once connected to the local server, you can navigate through the directories and download the files you need.

5. **Stop the Local Server** (Optional):
   - Once file transfer is complete, return to the Command Prompt on the first machine.
   - Press `Ctrl + C` to stop the local server.

By following these steps, you can easily transfer files between machines using a local server.
