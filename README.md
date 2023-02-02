# metabolism_model
A simple spatially embedded model of cells competing for space using a metabolism model that allows conservation of mass, photosynthesis and building of polymer based structures.

## Aims
I'm aiming to test a simple metabolism model that may later be incorporated into a more complex cell based morphogenesis model. Within this later model the role of the metabolism model will be to provide a simple accounting system for matter and energy, allowing the total mass in the system to be conserved and for energy to enter the system through photosynthesis and to pass between cells via mechanisms that can represent things like eating, lactation, regurgitation, external predigestion, nutrient absorbtion etc I want the simplest possible model that can achieve these kind of aims, as metabolism will not be the focus of the morphogenesis model.

## The Basic Model
The world is a two dimensional grid of squares, where biological cells can grow and compete for space, a maximum of one cell per square. The environment contains a diffusible monomer chemical building block which cells can absorb and build up into polymer chains of any length. The total monomer in the system, including dimer, trimer and larger forms, is conserved. Free monomer is spread out evenly as a global supply available to all cells, which reduces when cells bond them together into larger molecules and increases when those larger molecules are broken down. A polymer chain of any length can be built up by adding additional monomers to an existing chain. Only monomers freely diffuse, everything else, from dimer and above, are contained within individual cells.

Energy enters the system in the form of photons which cells capture and store in the chemical bonds that link monomer together. The photosynthesis reaction joins one dimer with one monomer to create one trimer and requires one photon. Energy is therefore stored when a dimer is extended into a trimer. Polymers, containing four or more monomers, are created by adding one new monomer at a time in a reaction which consumes one trimer.

Cells consist of cytoplasm and internal organelles, all made up of polymers. Cells can specialise by investing a lot of resource into growing a particular organelle to be as large as possible. Organelles are:

- cytoplasm (not really an organelle as such): the basic "stuff" of the cell excluding the other organelles, where it's store on dimer and trimer are kept
- chloroplasts: converts dimers into trimers by capturing photons and monomers 
- energy storage: contains long polymers which can be readily built up or broken down to store or release trimers
- cillia: allows the cell to actively move
- connectors: allows the cell to connect its cytoplasm to a neighbouring cell's and actively push or pull cytoplasm through the connection

### Photosynthesis Reaction
In this reaction occuring in the photosynthesis organelle one photon is absorbed and converts a dimer and a monomer into a trimer:

 M<sub>2</sub> + M + photon &rarr; M<sub>3</sub>

In this notation M represents a single monomer chemical building block, M<sub>2</sub> means two monomers chemically bonded together (a dimer) and M<sub>3</sub> represent three bonded together (a trimer).

In this reaction the cell converts one monomer and one dimer into a trimer. This reaction required a photo to provide the energy, which is stored in the new chemical bond created. Trimer therefore acts as an energy store for the cell.

### Energy Storage / Extending a Polymer
Here a single monomer is added to an existing polymer by consuming one trimer, therefore the polymer becomes longer by one unit. Here we require n >= 3:

  M<sub>n</sub> + M<sub>3</sub> &rarr; M<sub>n+1</sub> + 2 M

Why not consume one dimer instead of one trimer? In that case one bond would be broken in spliting the dimer in exchange for one bond created joining one monomer to the polymer. Therefore the reaction would be energetically neutral, and the reverse reaction ought to be equally likely where the monomer falls off again. When we break down the trimer we break two bonds in exchange for creating one new bond, therefore overall we use up one bond's worth of energy in order to actively drive the reaction in the forward direction.

### Energy Release / Breaking Down a Polymer
A polymer releases 3 monomers in the form of a trimer, n >= 6:

  M<sub>n</sub> &rarr; M<sub>n-3</sub> + M<sub>3</sub>

### Control System
Each cell has a neural network controlling how much effort it makes to build up each ctype of organelle, and if it activates cell movement or cytoplasm transport, and whether it divides. Each cell has an orientation and can rotate, and when it divides it tries to occupy an adjacent cell in a particular direction. Cell division could be triggered by reaching a certain size or by a control state trigger.

### Organelle Growth
The control system determines how much effort is allocated to growing or shrinking each of the organelle types. The rate of growth is the effort scaled by the aount of available trimer in the cytoplasm, which gets converted into dimer when consumed. The cell dies if the cytoplasm goes below a certain fraction of the cell volume.
