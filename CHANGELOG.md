## 0.15.0 (Unreleased)

UPGRADE NOTES:

* config: The `list` and `map` functions, both of which were deprecated since Terraform v0.12, are now removed. You can replace uses of these functions with `tolist([...])` and `tomap({...})` respectively. [GH-26818]
* cli: Interrupting execution will now cause terraform to exit with a non-0 status. [GH-26738]
* backend/atlas: the `atlas` backend, which was deprecated since v0.12, has been removed. [GH-26651]
* backend/gcs: The `path` config argument, which was deprecated since v0.11, has been removed. Use the `prefix` argument instead. [GH-26841]

ENHANCEMENTS:

* cli: Improved support for Windows console UI on Windows 10, including bold colors and underline for HCL diagnostics. [GH-26588]
* cli: The family of error messages with the summary "Invalid for_each argument" will now include some additional context about which external values contributed to the result. [GH-26747]
* communicator/ssh: Add support for Windows targets. The `remote-exec` provisioner now works correctly when connecting to Windows servers using SSH. Specify the `target_platform` as `"windows"` in the `connection` block. [GH-26865]

BUG FIXES:

* cli: Exit with an error if unable to gather input from the UI. For example, this may happen when running in a non-interactive environment but without `-input=false`. Previously Terraform would interpret these errors as empty strings, which could be confusing. [GH-26509]

EXPERIMENTS:

* Continuing the `module_variable_optional_attrs` experiment started in v0.14.0, there is now an experimental `defaults` function intended for use with it, to allow for concisely defining and merging in default values for any unset optional attributes in a deep data structure. The function is callable only when the `module_variable_optional_attrs` experiment is available, because it's intended for use only with incoming variable values that might have certain attributes unset.

## Previous Releases

For information on prior major releases, see their changelogs:

* [v0.14](https://github.com/hashicorp/terraform/blob/v0.14/CHANGELOG.md)
* [v0.13](https://github.com/hashicorp/terraform/blob/v0.13/CHANGELOG.md)
* [v0.12](https://github.com/hashicorp/terraform/blob/v0.12/CHANGELOG.md)
* [v0.11 and earlier](https://github.com/hashicorp/terraform/blob/v0.11/CHANGELOG.md)
