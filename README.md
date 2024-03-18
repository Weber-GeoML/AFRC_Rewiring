# afrc_rewiring

## Requirements
To configure and activate the conda environment for this repository, run
```
conda env create -f environment.yml
conda activate borf 
pip install -r requirements.txt
```

## Experiments
### 1. For graph classification
To run experiments for the TUDataset benchmark, run the file ```run_graph_classification.py```. The following command will run the benchmark with AFR3 rewiring using our heuristis:
```bash
python run_graph_classification.py --rewiring AFR3
```

To use AFR4 rewiring instead, simply replace AFR3 with AFR4 as the 'rewiring' argument. To use a different model or add more layers, add the --layer_type and --num_layers options
```bash
python run_graph_classification.py --rewiring AFR3 --layer_type GIN \
	--num_layers 8
```

### 2. For node classification
To run node classification, simply change the script name to `run_node_classification.py`. For example:
```bash
python run_node_classification.py --rewiring AFR4
```

## Other rewiring methods
To compare AFR3 against other rewiring methods, such as BORF, simply run
```bash
# runs BORF with our heuristic for choosing how many edges to add/ remove
python run_graph_classification.py --rewiring BORF
```

## Citation and reference
For technical details and full experiment results, please check [our paper](https://arxiv.org/abs/2309.09384).
```
@inproceedings{fesser2023mitigating,
  title={Mitigating Over-smoothing and Over-squashing using Augmentations of Forman-Ricci Curvature},
  author={Fesser, Lukas and Weber, Melanie},
  booktitle={The Second Learning on Graphs Conference},
  year={2023}
}
```
