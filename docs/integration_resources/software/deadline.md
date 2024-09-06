# Deadline

Shift integration in Deadline is in the works. Shift's Deadline integration is only available on Windows.
The Shift plugin for Deadline currently only works for execution of Shift workflows in batch mode or in Maya.

# Shift Plugin for Deadline Renderfarm

This guide will walk you through setting up the Shift plugin for the Deadline render farm. Depending on the version of Python used in your Deadline installation, follow the steps below to properly configure the plugin.

## Prerequisites

- Access to your Deadline repository.
- Admin rights to create new directories and modify settings in the Deadline Monitor.
- The Shift software installed.

## Step 1: Create the Plugin Folder

1. Navigate to the Deadline repository path: `<path_to_deadline_repository>/custom/plugins`.
2. Create a new folder named `Shift`.

## Step 2: Copy the Plugin Files

1. In the Shift installation directory, locate the `deadline` folder.  
   The path to this folder is `<path_to_the_shift_installation_folder>/deadline`.
2. Inside the `deadline` folder, there are two directories:
   - `python2.7`
   - `python3`
   
   Depending on which version of Python your Deadline installation uses:
   - If your Deadline uses **Python 2.7**, copy the contents of the `python2.7` folder.
   - If your Deadline uses **Python 3**, copy the contents of the `python3` folder.

3. Paste the copied files into the `Shift` folder you created in the Deadline repository.

## Step 3: Configure the Plugin in Deadline

1. Open **Deadline Monitor**.
2. Navigate to **Tools > Configure Plugins**.
3. In the list of plugins, select `Shift` to configure it.
4. Under the `Miscellaneous` tab, you will see fields to configure executable paths:
   - **Shift**: Set this to the path of the `shift_batch.bat` file. This file is located in the root of the Shift installation directory.
   - **Shift Maya**: Set this to the path of the `shift_maya_batch.bat` file. This file is also in the root of the Shift installation directory.

## Step 4: Configuring Environment Variables (Optional)

If you need to set up any environment variables for Shift while running on Deadline, there are two options:

### Option 1: Modify `PluginPreLoad.py`

1. Open the `PluginPreLoad.py` script that you copied earlier for the Shift plugin (found in `<path_to_deadline_repository>/custom/plugins/Shift`).
2. Add or modify any environment variables as needed.

### Option 2: Use a Custom PreLoad Script

You can create a custom Python file that sets up environment variables, and use it with the following environment variable:

1. Create a Python file that sets up the necessary environment variables.
2. Set the `SHIFT_DEADLINE_PLUGIN_PRELOAD_PATH` environment variable to point to this Python file.

This way, your custom script will run each time the Shift plugin is loaded in Deadline.

## Conclusion

Once you have completed the steps above, the Shift plugin should be fully integrated with your Deadline render farm. You can now submit jobs through Deadline using Shift or Shift Maya. If you run into any issues, make sure that the plugin paths and environment variables are set up correctly.
