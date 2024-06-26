# Project Idea: CRISPR Simulation and Chimera Maker

## The Idea

### Introduction

Charlie came up with the idea to create a simulation tool for editing DNA for CRISPR with artificial intelligence (AI). Because the idea appealed to me and I wanted to teach myself AI, I thought it would be a good idea to participate. The start-up of the project took a while, but in the end we got off to a good start.

The idea is to first collect data from the DNA genome of animals and create or normalize models to create a clean data model. We will use this data model to train the neural network.

Once we have the training data, we want to design and train the neural network. We train by linking our network results back to the results from the training data (back propagation).

To make the memory work efficiently, we split the DNA strands into pieces of 3, or condons. We store a condon in 1 byte instead of the usually used 3 bytes per condon of the 64 possible condons.

The model must be normalized so that, for example, the legs and head of each animal are in the same place. I don't think this is the same for every animal, we can also make different model types. The textures, material and normal map must be generated from the model output.

We also need to train the network on parts of the entire genome to obtain the full or partial output of the animal. Mixing DNA should produce a combination result for crating a chimera.

After successfully achieving this, our plan is to create a cell simulator to improve the overall result of the simulation.

### Features

Here are some keyfeatures that will be included in our CRISPR simulation and chimeramaker tool:

- **AI-basedprediction of CRISPR outcomes:** Using machine learning algorithms, our tool will be able to accurately predict the outcomes of CRISPR modifications, including targeted mutations, insertions or deletions. This will save time and resources for researchers, as they canevaluate the potential effects of modifications before conductingexperiments.
- **3D modeling from DNA:** The tool will be able to convert DNA sequences into 3D models, providing a visual representation of the outcome of the geneticstructure. This will allow researchers to better predict thepossible outcome of the modification.
- **Chimera maker:** Our tool will have the ability to merge DNA from different species and create chimeric DNA sequences. This feature can aid in thecreation of new organisms with specific traits and functions, advancing the capabilities of genetic engineering.
- **Identification of gene functions:** By analyzing the DNA sequence and using bioinformatics tools, our tool will be able to predict the functions of genes and help researchers identify potential targets for modifications.
- **Virtual CRISPR experiments:** The tool will have a built-in virtual laboratory where researchers can perform simulated CRISPR experiments and observe the outcomes. This will provide a safe and efficient way to test and optimize modifications before conducting experiments in a real laboratory.

### How It Works

* Users input parameters for organisms, such as size, complexity, and known genetic data.
* The simulation generates virtual organisms based on these parameters.
* The AI analyzes simulated organism data, learning patterns of cell development, genetic sequences, and relative complexity.
* As users provide unfinished genetic sequences, the AI predicts potential completions based on known evolutionary paths.
* Users can select organisms from the simulation or input external genetic data.
* The AI assesses compatibility and potential outcomes, guiding users in creating chimeras with predicted characteristics.

### Potential Applications

* **Research Aid**: Scientists can use the tool to explore evolutionary relationships between organisms; Assess the feasibility of creating novel organisms through genetic modifications.
* **Biomedical Innovation**: Aid in understanding genetic diseases by simulating affected organisms and potential gene therapies; Explore the creation of synthetic organisms for medical purposes.
* **Educational Tool**: Universities and students can use the tool to understand complex genetic concepts through interactive simulations; Demonstrate the impact of genetic modifications and evolution on organism development.

### Target Users

Our project aims tobe a valuable tool for genetic engineers, molecular biologists, bioinformaticians, and researchers working in the field of genetics. It will also be beneficial for students and educators in biology and biotechnology fields.

### Technology Stack

- **Programming language:** C will be the primary language used for this project due to it is a simplistic (no big clunky function libraries) and fast processing.
- **AI and machine learning:** C compatible Libraries will be used to implement AI-based prediction algorithms.
- **3D modeling:** OpenGL or a C language compatible game engine can be used to used to convert DNA sequences into 3D models and visualize them.
- **Bioinformatics:** C compatible Libraries will be used for gene analysis and prediction of gene functions.
- **Virtual laboratory:** OpenGL or a C language compatible game engine can be used to create avirtual laboratory environment where the CRISPR experiments can be simulated and observed.

### Conclusion

In conclusion, our CRISPR simulation and chimera maker project aims to provide a comprehensive tool for genetic engineering and research purposes. By combining AI, 3D modeling, and bioinformatics, it will be able to accurately predict the outcomes of CRISPR modifications, aid in the creation of chimeric DNA sequences, and provide a virtual laboratory for safe and efficient experimentation. We believe that this tool has the potential to significantly improve the efficiency and accuracy of genetic engineering and contribute to our understanding of genetics. 

## Appendix A: DNA Format Proposal

There are four DNA nucleotides: Adenine (A); Cytosine (C); Guanine (G); Thymine (T). Four possibilities can be stored into two bits. Since we want to read DNA as a condon as a packet of three, we need six bits to store one condon. There are eight bits in a byte, so two bits are left for another task as error checking or something else.

### The Condons

- *UUU (0x55)*:Phenylalanine (ASCII: U)
- *UUC (0x56)*:Phenylalanine (ASCII: V)
- *UUA (0x57)*:Leucine (ASCII: W)
- *UUG (0x58)*:Leucine (ASCII: X)
- *UCU (0x59)*:Serine (ASCII: Y)
- *UCC (0x5A)*:Serine (ASCII: Z)
- *UCA (0x5B)*:Serine (ASCII: \[)
- *UCG (0x5C)*:Serine (ASCII: \\)
- *UAU (0x65)*:Tyrosine (ASCII: e)
- *UAC (0x66)*:Tyrosine (ASCII: f)
- *UAA (0x6A)*:Stop (Termination codon) (ASCII: j)
- *UAG (0x6B)*:Stop (Termination codon) (ASCII: k)
- *UGU (0x75)*:Cysteine (ASCII: u)
- *UGC (0x76)*:Cysteine (ASCII: v)
- *UGA (0x7A)*:Stop (Termination codon) (ASCII: z)
- *UGG (0x7B)*:Tryptophan (ASCII: {)
- *CUU (0x95)*:Leucine (ASCII: •)
- *CUC (0x96)*:Leucine (ASCII: –)
- *CUA (0x97)*:Leucine (ASCII: —)
- *CUG (0x98)*:Leucine (ASCII: ˜)
- *CCU (0x99)*:Proline (ASCII: ™)
- *CCC (0x9A)*:Proline (ASCII: š)
- *CCA (0x9B)*:Proline (ASCII: ›)
- *CCG (0x9C)*:Proline (ASCII: œ)
- *CAU (0xA5)*:Histidine (ASCII: ¥)
- *CAC (0xA6)*:Histidine (ASCII: ¦)
- *CAA (0xA7)*:Glutamine (ASCII: §)
- *CAG (0xA8)*:Glutamine (ASCII: ¨)
- *CGU (0xA9)*:Arginine (ASCII: ©)
- *CGC (0xAA)*:Arginine (ASCII: ª)
- *CGA (0xAB)*:Arginine (ASCII: «)
- *CGG (0xAC)*:Arginine (ASCII: ¬)
- *AUU (0xB5)*:Isoleucine (ASCII: µ)
- *AUC (0xB6)*:Isoleucine (ASCII: ¶)
- *AUA (0xB7)*:Isoleucine (ASCII: ·)
- *AUG (0xB8)*:Methionine (Start codon; also codes for Methionine) (ASCII: ¸)
- *ACU (0xB9)*:Threonine (ASCII: ¹)
- *ACC (0xBA)*:Threonine (ASCII: º)
- *ACA (0xBB)*:Threonine (ASCII: »)
- *ACG (0xBC)*:Threonine (ASCII: ¼)
- *AAU (0xC5)*:Asparagine (ASCII: Å)
- *AAC (0xC6)*:Asparagine (ASCII: Æ)
- *AAA (0xC7)*:Lysine (ASCII: Ç)
- *AAG (0xC8)*:Lysine (ASCII: È)
- *AGU (0xC9)*:Serine (ASCII: É)
- *AGC (0xCA)*:Serine (ASCII: Ê)
- *AGA (0xCB)*:Arginine (ASCII: Ë)
- *AGG (0xCC)*:Arginine (ASCII: Ì)
- *GUU (0xD5)*:Valine (ASCII: Õ)
- *GUC (0xD6)*:Valine (ASCII: Ö)
- *GUA (0xD7)*:Valine (ASCII: ×)
- *GUG (0xD8)*:Valine (ASCII: Ø)
- *GCU (0xD9)*:Alanine (ASCII: Ù)
- *GCC (0xDA)*:Alanine (ASCII: Ú)
- *GCA (0xDB)*:Alanine (ASCII: Û)
- *GCG (0xDC)*:Alanine (ASCII: Ü)
- *GAU (0xE5)*:Aspartic Acid (ASCII: å)
- *GAC (0xE6)*:Aspartic Acid (ASCII: æ)
- *GAA (0xE7)*:Glutamic Acid (ASCII: ç)
- *GAG (0xE8)*:Glutamic Acid (ASCII: è)
- *GGU (0xE9)*:Glycine (ASCII: é)
- *GGC (0xEA)*:Glycine (ASCII: ê)
- *GGA (0xEB)*:Glycine (ASCII: ë)
- *GGG (0xEC)*:Glycine (ASCII: ì)
