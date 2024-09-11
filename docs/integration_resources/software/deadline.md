# Deadline

Shift integration in Deadline is in the works. The Shift plugin for Deadline is currently only available on Windows and supports the execution of Shift workflows in batch mode or within Maya.


# Shift Plugin for Deadline Renderfarm

This guide explains how to set up the Shift plugin for Deadline. The setup process varies depending on the version of Python used by the Deadline installation.

## Prerequisites

- Access to the Deadline repository.
- Administrative rights to create directories and modify settings in the Deadline Monitor.
- The Shift software installed.

## Step 1: Create the Plugin Folder

1. Navigate to the Deadline repository at `<path_to_deadline_repository>/custom/plugins`.
2. Create a new folder named `Shift`.

## Step 2: Copy the Plugin Files

1. Locate the `deadline` folder in the Shift installation directory.  
   The path is `<path_to_the_shift_installation_folder>/deadline`.
2. Inside the `deadline` folder, there are two directories:
   - `python2.7`
   - `python3`
   
   Depending on the Python version used in the Deadline installation:
   - For **Python 2.7**, copy the contents of the `python2.7` folder.
   - For **Python 3**, copy the contents of the `python3` folder.

3. Paste the copied files into the `Shift` folder created in the Deadline repository.

## Step 3: Configure the Plugin in Deadline

1. Open **Deadline Monitor**.
2. Navigate to **Tools > Configure Plugins**.
3. Select `Shift` from the list of plugins for configuration.
4. In the `Miscellaneous` tab, configure the executable paths:
   - **Shift**: Set the path to the `shift_batch.bat` file, located in the root of the Shift installation directory.
   - **Shift Maya**: Set the path to the `shift_maya_batch.bat` file, also located in the root of the Shift installation directory.

## Step 4: Configuring Environment Variables (Optional)

To set environment variables for Shift while running on Deadline, two options are available:

### Option 1: Modify `PluginPreLoad.py`

1. Open the `PluginPreLoad.py` script from `<path_to_deadline_repository>/custom/plugins/Shift`.
2. Add or modify any necessary environment variables.

### Option 2: Use a Custom PreLoad Script

A custom Python file can be created to set up environment variables, utilizing the following environment variable:

1. Create a Python file that configures the desired environment variables.
2. Set the `SHIFT_DEADLINE_PLUGIN_PRELOAD_PATH` environment variable to point to the custom Python file.

The custom script will then run each time the Shift plugin is loaded in Deadline.

## Conclusion

After completing the steps outlined above, the Shift plugin will be integrated with the Deadline render farm. Jobs can now be submitted through Deadline using Shift or Shift Maya. If any issues arise, ensure that the plugin paths and environment variable configurations are correct.
