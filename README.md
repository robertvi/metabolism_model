# metabolism_model
A simple spatially embedded model of cells competing for space using a metabolism model that allows conservation of mass, photosynthesis and building of polymer based structures.

## Aims
I'm aiming to test a simple metabolism model that may later be incorporated into a more complex cell based morphogenesis model. Within this later model the role of the metabolism model will be to provide a simple accounting system for matter and energy, allowing the total mass in the system to be conserved and for energy to enter the system through photosynthesis and to pass between cells via mechanisms that can represent things like eating, lactation, regurgitation, external predigestion, nutrient absorbtion etc I want the simplest possible model that can achieve these kind of aims, as metabolism will not be the focus of the morphogenesis model.

## The Basic Model
This is a two dimensional grid of squares, where biological cells can exist and grow. A maximum of one cell can exist per square or it can be empty. The grid represents living space in an environment that the cells are competing in for existence. The environment is filled with an inert medium (representing water in Earthling terms), containing a diffusible monomer (chemical building block) represented by the letter M in "chemical" equations later. Monomer is the only chemical substance found in the environment outside of the cells themselves. In addition energy is entering the system in the form of photons (light) shining on the squares from above, which cells can absorb in the manner of plant leaves or algae etc. to capture energy in the form of the chemical bonds that link monomers together into large molecules.

### Photosynthesis Reaction
In this reaction a cell capable of photosynthesis absorbs one photon and converts a dimer and monomer into a trimer:

 M<sub>2</sub> + M + photon &rarr; M<sub>3</sub>