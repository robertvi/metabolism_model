# metabolism_model
A simple spatially embedded model of cells competing for space using a metabolism model that allows conservation of mass, photosynthesis and building of polymer based structures.

## Aims
I'm aiming to test a simple metabolism model that may later be incorporated into a more complex cell based morphogenesis model. Within this later model the role of the metabolism model will be to provide a simple accounting system for matter and energy, allowing the total mass in the system to be conserved and for energy to enter the system through photosynthesis and to pass between cells via mechanisms that can represent things like eating, lactation, regurgitation, external predigestion, nutrient absorbtion etc I want the simplest possible model that can achieve these kind of aims, as metabolism will not be the focus of the morphogenesis model.

## The Basic Model
The world is a two dimensional grid of squares, where biological cells can grow and compete for space, a maximum of one cell per square. The environment contains a diffusible monomer chemical building block which cells can absorb and build up into polymer chains of any length. The total monomer in the system, including dimer, trimer and larger forms, is conserved. Free monomer is spread out evenly as a global supply available to all cells, which reduces when cells bond them together into larger molecules and increases when those larger molecules are broken down. A polymer chain of any length can be built up by adding additional monomers to an existing chain. Only monomers freely diffuse, everything else, from dimer and above, are contained within individual cells.

Energy enters the system in the form of photons which cells capture and store in the chemical bonds that link monomer together. The photosynthesis reaction joins one dimer with one monomer to create one trimer and requires one photon. Energy is therefore stored when a dimer is extended into a trimer. Polymers, containing four or more monomers, are created by adding one new monomer at a time in a reaction which consumes one trimer.

Cells consist of cytoplasm and internal organelles, all made up of polymers. Cells can specialise by investing a lot of resource into growing a particular organelle to be as large as possible. Organelles are:

- cytoplasm: the basic "stuff" of the cell, within which the other organelles exist
- photosynthesis: convert dimers into trimers by capturing photons and monomers 
- energy storage: contain long polymers which can be readily built up or broken down to store or release trimers
- nucleus: contains the genetic material, which must replicate each cell division
- cillia: allows the cell to actively move

### Photosynthesis Reaction
In this reaction occuring in the photosynthesis organelle one photon is absorbed and converts a dimer and a monomer into a trimer:

 M<sub>2</sub> + M + photon &rarr; M<sub>3</sub>

In this notation M represents a single monomer chemical building block, M<sub>2</sub> means two monomers chemically bonded together (a dimer) and M<sub>3</sub> represent three bonded together (a trimer).

In this reaction the cell converts one monomer and one dimer into a trimer. This reaction required a photo to provide the energy, which is stored in the new chemical bond created. Trimer therefore acts as an energy store for the cell.

### Energy Storage
Here a single monomer is added to an existing polymer by consuming one trimer:

  M<sub>n</sub> + M<sub>3</sub> &rarr; M<sub>n+1</sub> + 2 M

Why not consume one dimer instead of one trimer? In that case only one bond would be broken to split the dimer into two monomers, and one new bond created joining one monomer to the polymer. Therefore in crude terms the reaction would be energetically neutral, whereas we want to cell to be actively driving the reaction, otherwise the reverse reaction would be equally likely and the monomer would fall off again. When we break down the trimer we break two bonds in exchange for creating only one new bond, therefore overall we use up one bond's worth of energy in order to drive the reaction.