## Quick Start

### Prerequisites

Create a new conda environment and install dependencies:

```bash
# Create conda environment
conda create -n recode python=3.10.0
conda activate recode

# Install required packages
pip install -r requirements.txt
```

### Setup and Installation

**Important**: You must complete the following setup steps before running any experiments.

1. **Extract benchmark data:**
   ```bash
   cd data
   unzip temp.zip
   
   # Extract RepoExec benchmark
   cd ../benchmark/RepoExec
   unzip test-apps.zip
   
   # Extract DevEval benchmark
   cd ../DevEval
   tar -xzf data.tar.gz
   wget https://huggingface.co/datasets/LJ0815/DevEval/resolve/main/Source_Code.tar.gz
   tar -xvzf Source_Code.tar.gz
   ```

2. **Prepare structured context (required for experiments):**
   ```bash
   # For RepoExec benchmark
   bash src/context_formulation/structured_indexer/run.sh --dataset RepoExec
   
   # For DevEval benchmark  
   bash src/context_formulation/structured_indexer/run.sh --dataset DevEval
   ```


## Documentation
**Important** Before reproducing experiments, you must first train the DAR (Dependency-Aware Retriever) model 

For detailed instructions and comprehensive guides, please refer to:
- **[Training.md](docs/Training.md)** - DAR (Dependency-Aware Retriever) training guide including:
  - Dataset construction methodology
  - Model architecture and training procedures

- **[Reproduce.md](docs/Reproduce.md)** - Complete experimental reproduction guide including:
  - Benchmark setup and data preparation
  - Research questions reproduction (RQ1-RQ4)
  - Code generation pipeline
  - Evaluation and metrics calculation
