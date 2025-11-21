# Modular Data Processing Pipeline

* A flexible data pipeline system that can load, transform, validate, and export data. This is for learning and exploring purposes.*


## Roadmap

```bash
pipeline_project/
├── exceptions.py      # Start here
├── data_sources.py    # Step 2
├── transformers.py    # Step 3
├── pipeline.py        # Step 4
├── test_script.py     # Step 5
└── sample_data.json   # Test data
```

## Todo

### Abstract Base Classes *(ABC pattern)*

- `DataSource` - abstract base for all data loaders
- 'DataTransformer' - abstract base for transformations
- 'DataValidator' - abstract base for validation

### Concrete Implementations *(Inheritance + Polymorphism)*

- `CSVSource`, `JSONSource` - load from different formats
- `ColumnDropper`, `MissingValueHandler` - specific transformers
- `SchemaValidator`, `RangeValidator` - validation strategies


### Pipeline Orchestrator *(Composition)*

- `DataPipeline` class that chains sources → transformers → validators
- Uses composition to combine different components


### Error Handling *(Custom Exceptions)*

- `DataLoadError`, `ValidationError`, `TransformError`
- Proper exception hierarchy


### Properties & Validation

- Validate pipeline configuration
- Properties for accessing pipeline state


### Iterator Pattern

- Pipeline should be iterable, yielding processed batches


### Factory Pattern (Class methods)

- Alternative constructors for common pipeline configurations