# Budibase Select Component

https://github.com/pixelinfinito/select-component/assets/54587190/15b00590-f2ac-42f1-a662-001ae694bfad

## Overview

The Budibase Select Component plugin is designed to extend Budibase's capabilities by adding a Select Component. This functionality allows users to select items from a dropdown select component, especially when it is nested under a Data Provider. Furthermore, "On Change" events can be set to trigger specific actions.

For instance, consider a scenario with two tables - "Make" and "Cars". If a user wishes to display cars of a specific make, they can select the make from the dropdown list. Consequently, the table or another data provider updates to list only cars from the selected make. Given the component's seamless integration with built-in states, users can derive a multitude of functionalities.

## Installation

To incorporate the Budibase Select Component into your Budibase project, please follow these steps:

1. Copy the following repository link: `https://github.com/pixelinfinito/budibase-select-component`.
2. Launch Budibase and proceed to the "Plugins" section.
3. Select the "Add Plugin" option.
4. Choose the "GitHub Source".
5. In the "URL" section, paste the previously copied link.

Post these steps, the plugin will be automatically integrated into your Budibase environment.

## Features

![image](https://github.com/pixelinfinito/select-component/assets/54587190/07ccc9de-377f-4b15-b93d-a06da3b0d03f)

The Budibase Select Component is equipped with a variety of features:

1. **Multiple:**
   - Facilitates multiselect, enabling users to choose multiple items.

2. **Disabled State:**
   - Provides the option to disable the select input based on specific conditions or requirements.

3. **Data Provider:**
   - Designate the data provider from which the select component will obtain its data.

4. **Keep showing label on multiselect:**
   - Option to retain the placeholder text even when multiselect mode is active.

5. **On selection change callback:**
   - Configure specific actions to be executed when a selection undergoes a change.

---


## Contributing

If you're interested in contributing to the Budibase Select Component, follow these steps:

1. Fork this repository.
2. Create a new branch for your changes: `git checkout -b my-branch`
3. Make desired changes and commit: `git commit -m 'my changes'`
4. Push changes to your branch: `git push origin my-branch`
5. Open a Pull Request to the original repository.

## Build Instructions

To build this plugin, use the following command in your Budibase CLI:

```bash
budi plugins --build
```

For automatic rebuilds on changes:

```bash
budi plugins --watch
```

## Known Issues

As of now, there are no known issues. If you encounter any problems while using the Budibase Select Component, please open an issue in this repository and provide a detailed description of the problem.

## Learn More About Budibase

For more information about Budibase, visit the [Budibase GitHub Repository](https://github.com/Budibase/budibase).
