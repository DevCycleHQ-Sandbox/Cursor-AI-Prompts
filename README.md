# DevCycle Cursor AI Prompts

This repository contains a collection of prompts and resources for using with the [Cursor AI code editor](https://cursor.com/). These prompts are designed to be used with [DevCycle SDKs](https://docs.devcycle.com/sdks) and Cursor Composer (`command` -> `shift` -> `i`) to automatically cleanup variables, insert new varaibles, and help install DevCycle SDKs into an existing project. These prompts have been tested using `claude-3.5-sonnet`.

## [Cleanup Variable Prompt](./devcycle-cleanup-variable.md)

This prompt will help you cleanup DevCycle variables that are no longer needed in your codebase. Cursor Composer's ability to search across your entire codebase to identify where the variables are being used is impressive, while following the steps in the prompt to refactor and remove the variables as needed. To use this prompt, you just need to simply tell Cursor which variables you'd like to remove, and it will handle the rest. As with all AI code generation / refactoring, you should review the changes and make adjustments as needed.

Example Cursor Composer prompt using a `@File` command to refrence the prompt file:

- `` cleanup `config-to-upload` using instructions: @devcycle-cleanup-variable ``
- `` cleanup all variables in `DashboardComponents` using instructions: @devcycle-cleanup-variable ``

Example of Cursor's ability to reason through complex code to not only remove the unused variables, but also refactor the code.

![Code Cleanup Example](https://github.com/DevCycleHQ-Sandbox/Cursor-AI-Prompts/blob/main/screenshots/cleanup.png)

## [Insert Variable Prompt](./devcycle-insert-variable.md)

This prompt will help you insert DevCycle variables into your codebase. To use this prompt, you just need to simply tell Cursor where you would like to insert the variables and what the default value should be, and it will handle the rest. As with all AI code generation / refactoring, you should review the changes and make adjustments as needed.

Example Cursor Composer prompt using a `@File` command to refrence the prompt file:

- `Add a new feature flag arround the settings button using these instructions: @devcycle-insert-variable`
- `add a new feature flag arround each button in this component, using these instructions: @devcycle-insert-variable`

Example of Cursor inserting new DevCycle variables into the codebase:

![Code Insert Example](https://github.com/DevCycleHQ-Sandbox/Cursor-AI-Prompts/blob/main/screenshots/insert.png)

## [Install DevCycle SDK Prompt](./devcycle-install-sdk.md)

This prompt will help you install the DevCycle SDK into your project. To use this prompt, you just need to simply tell Cursor to install the SDK and configure it with your project's details. The prompt will attempt to detect the type of project you're working in and select the appropriate SDK to install. As with all AI code generation / refactoring, you should review the changes and make adjustments as needed.

Example Cursor Composer prompt using a `@File` command to refrence the prompt file:

- `install DevCycle SDK using: @devcycle-install-sdk`

### Adding DevCycle @Docs to Cursor

It is also recommended that you can refrence DevCycle's documentation directly from Cursor. To do this, you can use the `@Docs` command in Cursor Composer to search and insert documentation from DevCycle's website. To do this, simply type `@Docs` in a composer or chat windown and select `add new doc` and insert `https://docs.devcycle.com`. Passing in the new `@DevCycle` command will help provide more context to the AI about how to use DevCycle's SDKs.

![Adding DevCycle Docs to Cursor](https://github.com/DevCycleHQ-Sandbox/Cursor-AI-Prompts/blob/main/screenshots/add-doc.png)
