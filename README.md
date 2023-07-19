![Coeus Logo](coeus/assets/coeus-logo-light.png#gh-light-mode-only)
![Coeus Logo](coeus/assets/coeus-logo-dark.png#gh-dark-mode-only)

A Plotly dashboard to facilitate the visual exploration of gene neighborhood data. 

Coeus's primary use case is for the analysis of the genomic contexts of antimicrobial resistance (AMR) genes in bacterial genomes. It allows for easy visual comparison of gene order alongside gene neighborhood similarity-based clustering results showcasing differences between a gene's neighborhood across genomes. 

Coeus requires output files generated from [Gene-Order-Workflow](https://github.com/JTL-lab/Gene-Order-Workflow). Gene-Order-Workflow is a Nextflow based workflow to extract gene neighborhoods from assembly and annotation files for a user's specified genes of interest, derive similarity and distance matrices from BLAST All-vs-All bitscores, and perform unsupervised machine learning to assign neighborhood clusters. 

### Installation 
Installation is not currently supported for Windows. 

Coeus is set up with Poetry for dependencies management. 

1. Clone the repository and ``cd`` in:
```
git clone https://github.com/JTL-lab/Coeus.git
cd Coeus
```

2. Install Poetry: 
```
python3 -m pip install pipx
python3 -m pipx ensurepath
pipx install poetry
```

3. To then install all project dependencies, within the Coeus repository, run: 
```
poetry install
```

If you're interested in viewing details on the package dependencies and other options Poetry offers, within the Coeus repository you can run: 
```
poetry show --help 
```

### Using the dashboard
1. Ensure you have a `JSON` directory and `clustering` directory present somewhere on your local device (obtainable from running `Gene-Order-Workflow` on your dataset).

2. Once you've installed the required dependencies as shown in the Installation section, you can use the dashboard on your local machine by running the following within the src directory (`Coeus/coeus`): 
```
poetry run python coeus.py <full_path_to_data_directories>
```

Alternatively, if you would like to view the sample dataset, you can run: 
```
poetry run python coeus.py sample_data
```

3. Launch your preferred web browser to view the dashboard at http://localhost:8050/ !

### Acknowledgements 
To render gene order visualizations within the dashboard, this project uses code developed by Cameron Gilchrist (gamcil) for the D3 chart clustermap.js, which is used and modified here under the MIT license.

Citation: 
```
clinker & clustermap.js: Automatic generation of gene cluster comparison figures.
Gilchrist, C.L.M., Chooi, Y.-H., 2020.
Bioinformatics. doi: https://doi.org/10.1093/bioinformatics/btab007
```

