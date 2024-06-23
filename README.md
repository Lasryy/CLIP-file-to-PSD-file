
# clip_to_psd

A Python script to convert Clip Studio Paint (.clip) files to PSD format without any dependencies.

## Features

- Exports all basic layer properties (visibility, alpha lock, folder structure).
- Supports exporting text as vector text layers, a feature not available in the original Clip Studio Paint.
- Supports some filter layer types.

## Basic Usage

To convert a .clip file to a .psd file, run the following command:

`python clip_to_psd.py input.clip -o output.psd`

## Additional Options

To see more options, including how to export layers as raw PNG files or how to export the internal SQLite database without exporting pixel data, use the `--help` command-line option
