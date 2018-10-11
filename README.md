# FMI Coding Style Rules for IntelliJ IDEA

This is a _read-only_
[settings repository](https://www.jetbrains.com/help/idea/sharing-your-ide-settings.html#settings-repository)
containing FMI's code style formatting rules and inspection rules for [IntelliJ
IDEA](https://www.jetbrains.com/idea/). Anybody contributing to FMI repositories
should apply these settings in addition to any language-specific rules (see
[fmi-codestyle-*](https://github.com/fmidev?utf8=%E2%9C%93&q=fmi-codestyle)
repositories).

In addition to code style formatting scheme, two inspection profiles are provided:
* **FMI Required** - rules that code must pass. Violations must be fixed, false
  positives shall be suppressed.
* **FMI Suggested** - rules serving as hints for developer. This is the
  recommended active profile during development.

Rules are provided for following languages:
* Java
* XML



## Getting the rules into IDEA

There are different ways to get the rule sets into IDEA:
1. dynamically, enabling automatic updates, by configuring the repository as
   read-only settings repository
2. statically, without automatic updates, by importing rule files


### Configuring as settings repository

Follow these steps to configure this repository as IDEA read-only settings
repository.

1. Ensure you have **Settings Repository** plugin enabled in the
   **Settings/Preferences** dialog under **Plugins**.
2. In the **Settings/Preferences** dialog, click **Settings Repository** under
   **Tools**.
3. Click `+` and add the _clone url_ of this repository.

If you already haven't set up a read-write settings repository, set up (a local)
one.

1. Select **File | Settings Repository** from the main menu.
2. Specify the url of the repository. For a local repository, use a path like:
   ```
   <home-dir>/idea-settings-repository.git
   ```
   You may choose any location you desire, but it is recommended to include the
   **.git** suffix in the name.
3. Click **Overwrite Local** (or **Merge** or **Overwrite Remote**). If you get
   notified about non-existent settings repository at specified location, click
   **Create** to create a new local settings repository at specified location.

If you want more control on when rules are automatically updated, make a bare
clone this repository and configure the local repository instead of the remote
repository as read-only settings repository. Then updates are applied only when
you fetch changes from remote repository to local.


### Importing rules statically

Follow these steps to import rules statically into IDEA.

1. Download the repository contents either by cloning or downloading it.
2. In the **Settings/Preferences** dialog, click **Code Style** under
   **Editor**.
3. In the **Scheme** area, click the tools menu button and select **Import
   Scheme** and choose all files from the **codestyles** directory of this
   repository, one at a time.
3. In the **Settings/Preferences** dialog, click **Inspections** under
   **Editor**.
4. In the **Profile** area, click the tools menu button and select **Import
   Profile** and choose all files from the **inspection** directory of this
   repository, one at a time.

To update rules redo all the steps above.



## Applying the rules

Follow these steps to apply the FMI rules within IDEA.

1. In the **Settings/Preferences** dialog, click **Code Style** under
   **Editor**.
2. Select **FMI** in the **Scheme** drop-down menu.
3. In the **Settings/Preferences** dialog, click **Inspections** under
   **Editor**.
4. Select desired FMI profile (**FMI Suggested** is recommended) in the
   **Profile** drop-down menu.
5. Accept changes by clicking **OK**.
6. Open any Java source file.
7. In the **Code | Show Reformat File Dialog** dialog select
   * [X] **Whole file** for Scope
   * [X] **Optimize imports**
   * [X] **Rearrange code**
8. Click **Run** to close the window.

From now on, always use **Code | Reformat Code** on each source file.

**NOTE:** Do _**not**_ apply **Optimize imports** on XLST files as it breaks
the transformation style.

If you're mainly working with FMI code, you should consider configuring the
rules in the **Project Defaults | Settings** dialog.
