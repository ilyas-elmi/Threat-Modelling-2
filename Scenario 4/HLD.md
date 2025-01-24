```mermaid
flowchart TD
    Insider["Insider (Employee)"] -->|Logs in with valid credentials| SOEApp["SOE Desktop Application"]
    SOEApp -->|Sends queries| BackendServer["SOE Backend Server"]
    BackendServer -->|Accesses data| Database["SOE Database"]
    Database -->|Returns patient data| BackendServer
    BackendServer -->|Displays data| SOEApp
    SOEApp -->|Exports data| ExternalDevice["External Device/Network"]
    SOEApp -->|Sends modification requests| Database
    Database -->|Records changes| BackendServer
    BackendServer -->|Sends updated data| SOEApp
    Insider -->|Attempts to erase logs| LogSystem["Logging and Monitoring System"]