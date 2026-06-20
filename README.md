# Li_ads_ML

An automated workflow to generate a database of adsorption energies and a Graph Neural Network (GNN) model to predict them are presented. PyMatGen tools are used to generate surfaces from Materials Project’s crystalline structures and to identify adsorption sites on them. The GNN model, based on Xie and Grossman's CGCNN model (2018), is implemented in PyTorch and designed to run on GPUs.

This project aims to help to identify materials suitable for use as anode current collectors in Anode-Free Lithium Batteries (AFLB). Pande and Viswanathan showed that the adsorption energy of Lithium (Li) on a metallic crystal's surface can be used as a descriptor of the material's performance as a current collector.[^1]

Using the automatic workflow and the trained model, a database of 1507 adsorption energies was created. The considered substrates are made of pure transition metals, Li, Mg, Ca, B, Al, Ga, Si, Sn, Ge and Pb, as well as their alloys with Li.

The `ads_energies_calculations` directory contains the complete workflow for computing adsorption energies. It includes a jupyter notebook responsable for:
- Selecting materials
- Creating slabs from them
- Creating the `.in` files for Quantum ESPRESSO (QE) to relax the surfaces and compute the adsorption energies
- Identifying the adsorption sites on surfaces
- Extracting the results from the QE's `.out` files.

[^1] V. Pande, V. Viswanathan. **“Computational Screening of Current Collectors for Enabling Anode-Free Lithium Metal Batteries”**. In: ACS Energy Letters 4.1 (2019), pp. 2952-2959. doi: 10.1021/acsenergylett.9b02306.

