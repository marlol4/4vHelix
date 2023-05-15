# 4vHelix - Software for design of A-trail based structures with 4HB

## Introduction
This program allows the design of DNA origami nanostructures based on 4-helix bundles (4HB). The software uses the BSCOR-vHelix scaffold routing to create a mesh based on DNA from a PLY input file, and then allows to select edges to be reinforced with 4HB. The software outputs a caDNAno JSON file, and the GUI can be used to generate the nucleotide sequence for the staples and mini scaffolds needed for the folding.
The software for the design of the structures was made by Marco Lolaico and the majority of the code for the GUI and the sequence generating routine was made by [Sebbe Blokhuizen](https://github.com/SBlokhuizen).

## Usage
The program can be run using the command:
```python
python 4vHelix.py
```

## Inputs 
The software accepts different inputs.

- .ply file input: If the input is a .ply mesh, the BSCOR routing algorithm has to be run first. BSCOR can be run directly in the GUI, specifying the scaling for the mesh. More information about BSCOR can be found at [bscor](https://github.com/mohamma1/bscor). The resulting files can then be used for the next step in the design of the DNA origami. 
- .rpoly, .ply, .ntrail: These 3 files are required for the design of the reinforced structures

## Outputs
The edge reinforcement routine generates a cadnano output file:
- filename.json - contains the cadnano json file of the structure including reinforcement of the selected edges.

The sequence designer/generator will generate three output files:

- scaffolds_filename.txt - contains the sequences of the scaffold strands. Moreover, it contains the start and end location, and the length of each scaffold.
- staples_filename.txt - contains the sequences of the staple strands. Moreover, it contains the start and end location, and the length of each staple.
- visualized_sequence_filename.txt - contains a nicely formatted visualization of the scaffold and staple sequence data, analogous to the visual representation in cadnano. This might be useful for checking the final results.
More information about the sequence generating routine can be found [here](https://github.com/ItsTheSebbe/SequenceDesigner).

## Example Workflow
The following is an example for workflow of reinforcing edges.
- Launch 4vHelix.py.
- Open .rpoly file.
- Open .ply file.
- Open .ntrail file.
- Select edges that need to be reinforced.
- Press "Reinforce selected edges".
- The cadnano .json file will be the output.

In case one wants to use the GUI to also run the BSCOR scaffold routing the following is the workflow:
- Open .ply file 
- Define a scaling value
- Press "Rout Mesh".
The software will run BSCOR and it will output the files for the design. To reinforce the edges, at this point the previous workflow can be followed.

To run the sequence designed the cadnano file needs to present a break, for the scaffold to start and finish. The workflow to run the sequence designer is as follow:
- Press "Run sequence designer"
- Select which scaffold you want to use (if your desired scaffold is not in here, you can simply add it to the scaffold_files folder).

## Citing 

Please cite this publication for any work that uses this software:

**Computer-Aided Design of A-Trail Routed Wireframe DNA Nanostructures with Square Lattice Edges**\
Marco Lolaico, Sebbe Blokhuizen, Boxuan Shen, Yang Wang, and Björn Högberg\
ACS Nano 2023 17 (7), 6565-6574\
DOI: 10.1021/acsnano.2c11982\
