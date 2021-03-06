![build](https://github.com/rajyraman/pcf-actions-starter/workflows/build/badge.svg)
# Summary

The repo demonstrates how you can use GitHub actions to build a PCF project, as well as how you can automate the releases.

# Setup

After creating your folder with the PCF component, copy the .github folder on this repo into root on your PCF folder. On the build.yml, update this environment variable: _msbuildtarget_. This is so that MSBuild knows the target project to build, and the release artifacts will have the right names. The solution name is what is in the solution.xml file (uniquename). The formats used for the release are _[solutionname]\_v[package.json version]\_managed.zip_ and _[solutionname]\_v[package.json version]\_unmanaged.zip_. As a convention I use _Solution/[Solution Name]_ to hold the files for solution build.

# Building

The build.yml workflow will build everytime a commit is pushed or an PR is merged into master.

# Release

When you push a tag that is in the format _vx.x.x_, the release steps will run after the build steps. The release steps also copy the artifacts and put it in the release.
