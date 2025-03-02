# Clip Studio Paint .CLIP file to Photoshop .PSD file

**clip_to_psd** is a standalone Python script for converting Clip Studio Paint (.clip) files into editable Photoshop (.psd/psb) files. Unlike traditional export tools, it preserves advanced layer properties—including editable text, filter layers, gradients, and more—without relying on external software.  

*(FR: clip_to_psd est un script Python autonome permettant de convertir des fichiers .clip de Clip Studio Paint en fichiers PSD/PSB éditables, tout en conservant des fonctionnalités avancées telles que les calques de texte modifiables, les calques de filtres, les dégradés, etc.)*

## Features

- **Comprehensive Layer Export**  
  Retains the full layer structure (order, folders, visibility, blending modes, opacity, and color tags) and exports pixel data, masks, and editing properties. Draft layers are automatically set to invisible in the exported PSD.

- **Editable Text Layers**  
  Converts text layers into editable vector text in Photoshop, preserving transformation, color, typography, and alignment settings.

- **Filter Layer Support**  
  Supports exporting common filter layers (HSL, Levels, Brightness/Contrast, and Curves) so that they remain editable within Photoshop.

- **Outline Effects**  
  Transfers outline effects as PSD stroke properties, including those applied to text layers.

- **Gradients and Solid Color Layers**  
  Exports both gradient layers and solid fill layers with advanced settings, offering vector (editable) or rasterized versions when pixel data is available.

## Requirements

- **Python 3.6+** (Python 3.9 or later is recommended for full functionality)  
- **Pillow (Optional)**: Required if you want PSD thumbnail previews or to export layers as PNG files.  
  Install via:
  ```bash
  pip install Pillow
  ```
- No other external dependencies are needed.

## Installation

1. **Clone or Download the Repository**  
   Fork and clone the repository to your local machine.
   
2. **Ensure Python is Installed**  
   Verify that Python 3 is installed (use `python --version`).

3. **(Optional) Install Pillow**  
   If you wish to export image previews or individual layers as PNGs, install Pillow with:
   ```bash
   pip install Pillow
   ```

## Basic Usage

Convert a `.clip` file to PSD by running:

```bash
python clip_to_psd.py input.clip -o output.psd
```

This command reads `input.clip` and writes an editable Photoshop file named `output.psd`.

## Advanced Options

Run the script with the `--help` flag to see additional options:

```bash
python clip_to_psd.py --help
```

Options include:
- **Output Directory**: Export individual layers as PNG files using `--output-dir`.
- **Preview Export**: Export a downscaled canvas preview image with `--output-preview-image`.
- **Bypass PIL Dependency**: Use `--blank-psd-preview` to avoid importing the Pillow library.
- **Layer Export Modes**: Customize text and gradient layers to be exported as raster or vector layers using `--text-layer-raster`, `--text-layer-vector`, `--gradient-layer-raster`, and `--gradient-layer-vector`.

## Limitations

- **Vector Layers**:  
  True vector layers are always rasterized if no pixel data is available. This is due to limitations in the .clip format itself.

- **Advanced Effects**:  
  Effects such as Color Balance, Posterization, Binarization, and Gradient Map are not supported.

- **Animation Data**:  
  Animation timelines and related data are not exported.

- **External References**:  
  Any external file references are not included in the export.

- **Compatibility Note**:  
  Some exported layers (e.g., backgrounds defined as solid fill layers) may appear transparent or altered when reopened in Clip Studio Paint since CSP cannot interpret PSD vector or solid fill layers.

## Contributing

Contributions, forks, and improvements are welcome! Feel free to open pull requests or issues if you have suggestions or fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
