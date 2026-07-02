# Remote computer control / Django course project

### Features:

1. **Remote Command Execution**  
   In the **Chat** section you can communicate with the computer if it is online (the program is running).  
   Messages are executed in the console, and the result is returned as a text response.

2. **Closing specific processes at regular intervals**  
   In the **Programs** section you can add a program to monitoring.  
   You can also select which computer this process (program) belongs to.  
   In the computer's **Detail** view at the bottom there is a switch button **"monitoring"** to enable/disable automatic closing of specified programs. You can also set the closing interval.

3. **Saving frequently used commands**  
   In the **Commands** section you can create detailed descriptions of commands and save them.  
   If you have many commands, there is an advanced search by name.

## Usage:
1. Download the ZIP file containing the control software to the computer you intend to control.
2. Extract the files from the ZIP archive and launch the program.
3. A `.env` file containing the computer name and password will be generated.
4. Register the computer on the server.

### How to set your own password/ID for the computer

1. Open the existing `.env` file.
2. Replace the password and ID.

    **Important!**  
    If you change only the password but leave the computer ID (name) unchanged, the computer will not be able to connect to the server.  
    
    You **must** change both the password and the ID. Changing the ID will create a **new computer** in the database.
    
    If you don’t want a “ghost” computer to remain in the database (old ID stays in DB but is unused), 
    you should create the `.env` file with the correct parameters **before** running the program (`.exe`).

### Initial data for the `.env` file:

```env
NAME=Computer-000000
URL=wss://192.168.50.16
PASSWORD=password12345
```

### Restrictions and details for `.env` parameters:

- **PASSWORD**: No restrictions — you can use any letters, numbers, and any length.

- **NAME**: Maximum 100 characters.  
  It does **not** have to start with "Computer", but it **must be unique**.

### Detailed description of `.env` parameters:

- `NAME` — Computer ID (must be unique).
- `URL` — WebSocket address for connection. Change it to your own IP if it differs from the default.
- `PASSWORD` — Password for the computer.
