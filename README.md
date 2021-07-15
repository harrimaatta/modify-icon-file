# modify-icon-file

## Prerequirements
This workflow is using [ImageMagick](https://imagemagick.org/). 

## How to use 
There is one required parameter, an icon file naturally, and few optionals.
```YAML
name: 'Modify App Icon'
description: 'Add version info onto app icon'
inputs:
  icon-file:
    description: 'Path of the icon'
    required: true
    default: 'icon.png'
  first-line:
    description: 'First line'
    required: false
  second-line:
    description: 'Second line'
    required: false
  third-line:
    description: 'Third line'
    required: false
runs:
  using: "composite"
  steps:
    - run: ${{ github.action_path }}/modify-icon.sh ${{ inputs.icon-file }} ${{ inputs.first-line }} ${{ inputs.second-line}} ${{ inputs.third-line }}
      shell: bash
```