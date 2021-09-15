# DrawMolToMPL: Quickfix for RDKit drawing with matplotlib

A quickfix for *rdkit.Chem.Draw.MolToMPL* to save drawings as **vector graphics**.

<img src="images/example.png" width="600">


## What is this for?

*DrawMolToMPL* generates a drawing of *rdkit.Chem.rdchem.Mol* objects by matplotlib line graphics, and thus it can be saved as a **vector image**.

I had a problem when I tried to output RDKit molecular graphics into a PDF file. If I convert it into a PIL image by *rdkit.Chem.Draw.MolToImage* for matplotlib subplots, then the output quality was in a low resolution because it's a pixel image. But, apparently SVG-based drawings (like *rdkit.Chem.Draw.rdMolDraw2D.MolDraw2DSVG*) cannot simply be saved to a file. In particular, it cannot work with matplotlib subplots. 

## How to use this?

See [example.ipynb](example.ipynb).

## To work with matplotlib subplots

Internally *DrawMolToMPL* draw a molecule in the [0,1]x[0,1] area, and returns (xlim, ylim) representing its bounding box. So you can work using this information as you like.

<img src="images/output.png" width="600">

