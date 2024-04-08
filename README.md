# Overview

This repo stores our public custom extensions for Tilt - this is meant to be used alongside the default extension repo, and not as a replacement.

Please note that the only supported platform is MacOS. Other POSIX platforms may or may not work; and Windows is 100% not supported.

## Initial Setup

Within your own Tilt file you need to first inform Tilt about this repo, you can copy this line as-is **above any load() functions**:

```python
v1alpha1.extension_repo(name="soon", url="https://github.com/thisissoon/tilt-extensions", ref="main")
```

## Loading custom extensions

Loading extensions is generally the same as before, except we need to add an extra line for each extension to explicitly tell Tilt to use this repo for each of our custom extensions:

```python
v1alpha1.extension(name="gcp-impersonate", repo_name="soon", repo_path="gcp-impersonate")
load("ext://gcp-impersonate", "create_impersonation_credentials")
```

It's a bit ugly, but it's a hard requirement.

## Creating a new extension

1. Clone this repo.
2. Add a new folder with the same name as your extension.
3. Create a Tiltfile in the root of your new folder, everything can be `load()`ed by default by user Tiltfiles, so just write Tilt as normal.
4. Please add a README.md
5. Please add an `example` folder, with a Tiltfile inside to demonstrate how your extension works - it doesn't neccessarily need to work or do much.
6. Please add your extension into the list in this README.
7. Open an MR, etc. etc.

# Extensions

* [gcp-impersonate](./gcp-impersonate/) - Provides an easy way to setup service account impersonation for GCP.
