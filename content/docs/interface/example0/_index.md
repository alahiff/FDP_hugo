---
weight: 30
title: "Simple working examples"
---

<span style="font-size:12pt; color:red">Note that this is a living document and the following is subject to change. </span>

# Simple working examples (with Data Pipeline API functionality)

## Empty code run

### User written *config.yaml*

```yaml
run_metadata:
  description: An empty code run
  local_data_registry_url: https://localhost:8000/api/
  remote_data_registry_url: https://data.scrc.uk/api/
  default_input_namespace: SCRC
  default_output_namespace: soniamitchell
  default_data_store: /Users/SoniaM/datastore/
  local_repo: /Users/Soniam/Desktop/git/FAIRDataPipeline/FDP_validation/
  script: |- 
    R -f simple_working_examples/empty_script.R ${{CLI.CONFIG_DIR}}
```

### Working *config.yaml*

`fair run` should create a working *config.yaml* file, which is read by the Data Pipeline API. In this example, the working *config.yaml* file is pretty much identical to the original *config.yaml* file, only `${{CLI.CONFIG_DIR}}` is replaced by the directory in which the working *config.yaml* file resides.

```yaml
run_metadata:
  description: An empty code run
  local_data_registry_url: https://localhost:8000/api/
  remote_data_registry_url: https://data.scrc.uk/api/
  default_input_namespace: SCRC
  default_output_namespace: soniamitchell
  default_data_store: /Users/SoniaM/datastore/
  local_repo: /Users/Soniam/Desktop/git/FAIRDataPipeline/FDP_validation/
  script: |- 
    R -f simple_working_examples/empty_script.R /Users/SoniaM/datastore/coderun/20210511-231444/
```

## Write data product

### User written *config.yaml*

```yaml
run_metadata:
  description: Write an array
  local_data_registry_url: https://localhost:8000/api/
  remote_data_registry_url: https://data.scrc.uk/api/
  default_input_namespace: SCRC
  default_output_namespace: soniamitchell
  default_data_store: /Users/SoniaM/datastore/
  local_repo: /Users/Soniam/Desktop/git/FAIRDataPipeline/FDP_validation/
  script: |- 
    R -f simple_working_examples/write_array.R ${{CLI.CONFIG_DIR}}

write:
- data_product: test/array
  description: test array with simple data
  version: 0.1.0
```

### Working *config.yaml*

`fdp run` should create a working *config.yaml* file, which is read by the Data Pipeline API. In this example, the working *config.yaml* file is pretty much identical to the original *config.yaml* file, only `${{CLI.CONFIG_DIR}}` is replaced by the directory in which the working *config.yaml* file resides.

```yaml
run_metadata:
  description: Write an array
  local_data_registry_url: https://localhost:8000/api/
  remote_data_registry_url: https://data.scrc.uk/api/
  default_input_namespace: SCRC
  default_output_namespace: soniamitchell
  default_data_store: /Users/SoniaM/datastore/
  local_repo: /Users/Soniam/Desktop/git/FAIRDataPipeline/FDP_validation/
  script: |- 
    R -f simple_working_examples/write_array.R /Users/SoniaM/datastore/coderun/20210511-231444/

write:
- data_product: test/array
  description: test array with simple data
  version: 0.1.0
```

## Read data product

### User written *config.yaml*

```yaml
run_metadata:
  description: Read an array
  local_data_registry_url: https://localhost:8000/api/
  remote_data_registry_url: https://data.scrc.uk/api/
  default_input_namespace: SCRC
  default_output_namespace: soniamitchell
  default_data_store: /Users/SoniaM/datastore/
  local_repo: /Users/Soniam/Desktop/git/FAIRDataPipeline/FDP_validation/
  script: |- 
    R -f simple_working_examples/read_array.R ${{CLI.CONFIG_DIR}}

read:
- data_product: test/array
  component: level/a/s/d/f/s
  version: 0.1.0
```

### Working *config.yaml*

`fdp run` should create a working *config.yaml* file, which is read by the Data Pipeline API. In this example, the working *config.yaml* file is pretty much identical to the original *config.yaml* file, only `${{CLI.CONFIG_DIR}}` is replaced by the directory in which the working *config.yaml* file resides.

```yaml
run_metadata:
  description: Read an array
  local_data_registry_url: https://localhost:8000/api/
  remote_data_registry_url: https://data.scrc.uk/api/
  default_input_namespace: SCRC
  default_output_namespace: soniamitchell
  default_data_store: /Users/SoniaM/datastore/
  local_repo: /Users/Soniam/Desktop/git/FAIRDataPipeline/FDP_validation/
  script: |- 
    R -f simple_working_examples/read_array.R /Users/SoniaM/datastore/coderun/20210511-231444/

read:
- data_product: test/array
  component: level/a/s/d/f/s
  version: 0.1.0
```