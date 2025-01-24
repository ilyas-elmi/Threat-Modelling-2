```mermaid
graph TD
    %% Entities
    Insider["Insider (Employee)"] -->|Logs in with valid credentials| SOEApp["SOE Desktop Application"]
    
    %% Accessing Data
    SOEApp -->|Queries patient data| BackendServer["SOE Backend Server"]
    BackendServer -->|Processes query| Database["SOE Database"]
    Database -->|Returns sensitive data| BackendServer
    BackendServer -->|Sends data to SOEApp| SOEApp
    SOEApp -->|Displays patient data| Insider

    %% Data Exfiltration
    SOEApp -->|Exports data| ExternalStorage["External Storage (USB/Cloud)"]
    SOEApp -->|Sends data| Email["Email or File Sharing Service"]
    
    %% Data Manipulation
    Insider -->|Issues modification commands| SOEApp
    SOEApp -->|Alters patient records| BackendServer
    BackendServer -->|Updates database| Database
    Database -->|Reflects changes| BackendServer
    BackendServer -->|Sends manipulated data| SOEApp

    %% Covering Tracks
    Insider -->|Attempts to erase activity logs| BackendServer
    BackendServer -->|Processes log changes| LogSystem["Logging and Monitoring System"]