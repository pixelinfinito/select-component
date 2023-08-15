# Budibase Select Component

<img src="https://github.com/pixelinfinito/budibase-select-component/blob/main/select.png?raw=true" />

## Description

Budibase Select Component is a custom selection input component designed for seamless integration with Budibase applications. This component is built upon the https://github.com/pixelinfinito/budibase-select-component project and extends its functionality to cater to specific Budibase requirements.

## Installation

To install the Budibase Select Component as a plugin for Budibase, follow these steps:

1. Copy the repository link: `https://github.com/pixelinfinito/budibase-select-component`.
2. Open Budibase and navigate to the "Plugins" section.
3. Click "Add Plugin."
4. Select "GitHub Source."
5. Paste the copied link into the "URL" section.

The plugin will be automatically installed within your Budibase project.

## Usage

After successfully installing the Budibase Select Component plugin, you can start incorporating it into your application. This component enhances the selection input capabilities of Budibase, offering you extended options and customization.

To use the component:

1. First add a data source
1. **Import Component:**
   - <img src="https://github.com/pixelinfinito/budibase-select-component/blob/main/Captura%20de%20ecr%C3%A3%202023-08-15%20095624.png?raw=true" />

2. **Define Options:**
   - <img src="https://github.com/pixelinfinito/budibase-select-component/blob/main/Capturadeecr%C3%A32023-08-15094427.png?raw=true" />

3. **Callback Function:**
   - Optionally, define a callback function for selection changes.

## Features

Budibase Select Component offers the following features:

1. **Multiselect:**
   - Enable multiselect option for selecting multiple items.

2. **Disabled State:**
   - Disable the select input when needed.

3. **Required Validation:**
   - Set the select input as required for form validation.

4. **Dataprovider Label:**
   - Customize the label for the dataprovider.

5. **Selection Change Callback:**
   - Define a callback function to execute on selection changes.

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
