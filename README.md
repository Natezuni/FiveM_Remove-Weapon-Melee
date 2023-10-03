# Remove Weapon Melee Script

This FiveM script allows you to remove melee when holding a weapon. This is useful in cqb situations where you don't want to trigger the automatic postol whip mechanic on people close to you.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Directory Structure](#directory-structure)
- [Config File Security Considerations](#config-file-security-considerations)
- [Dependencies](#dependencies)

## Installation

1. Ensure you have a functioning [FiveM server](https://fivem.net/) set up.
2. Copy the directory with the name of the current script into your server's resources folder.

## Usage

1. Start your FiveM server.
2. If the script has been added while the server is running execute `refresh` in the console
3. To start the script execute `start script-name`

### Optional Automatic Script Startup

4. Edit your server.cfg file and add the resource name to the `resources` section.

   ```ini
   ensure script-name
   ```

5. Save the server.cfg file.
6. Restart your FiveM server.

## Directory Structure

Make sure your script follows these naming conventions and directory structure:

### Client Scripts

Client scripts should be created in the `/[resource-name]/Client/` directory and follow the naming
convention: `cl_*.lua`.

Example client script path: `/[resource-name]/Client/cl_client.lua`

### Server Scripts

Server scripts should be created in the `/[resource-name]/Server/` directory and follow the naming
convention: `sv_*.lua`.

Example server script path: `/[resource-name]/Server/sv_server.lua`

### Config File

The `config.lua` file, which can be found in the root directory of the script is a crucial component of this script,
serving as a central repository for configuration settings. It plays a vital role in customizing various aspects of the
script's behavior. Some common uses for the `config.lua` file include:

- **Customization:** You can modify parameters in the `config.lua` file to tailor the script to your specific needs.
  This includes adjusting in-game features, settings, and behaviors.

- **Ease of Maintenance:** Separating configuration data into a dedicated file simplifies maintenance. You can make
  adjustments without delving into the script's core code.

- **Accessibility:** Configuration settings are often used by both server-side and client-side scripts, making
  the `config.lua` file an accessible and centralized location for shared data.

However, it's crucial to be aware of potential security considerations when storing sensitive information in this file. Please review the following security considerations:

## Config File Security Considerations

Storing sensitive information, such as webhook links and API keys, in a config file presents security challenges:

1. **Accessibility:** Config files are often declared as shared, accessible both on the server and client sides of the
   script. This makes them vulnerable to unauthorized access.

2. **Risk of Exposure:** Modders or malicious actors can exploit vulnerabilities to access config files. If the config
   contains sensitive data, it can be exposed to potential threats.

3. **Data Breaches:** In case of a security breach, sensitive information like API keys or webhook links could be
   compromised, potentially leading to unauthorized access or misuse.

To enhance security, consider alternative methods such as storing sensitive data in a secure database and retrieving it
as needed to minimize the risk associated with config file storage.
