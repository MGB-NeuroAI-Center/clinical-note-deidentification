# Clinical Note Deidentification

## Description
This project automates the de-identification of clinical notes by detecting and anonymizing sensitive entities such as MRN numbers and dates using the Presidio library.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites
- **Python** 3.8+
- **pip** (Python package manager)
- **PyCharm or VSCode** recommended for development
- No database required
- No system-level permissions or API keys needed

## Installation

### Setup Instructions
1. Clone the repository
   ```bash
   git clone https://github.com/MGB-NeuroAI-Center/clinical-note-deidentification.git
   cd clinical-note-deidentification
   ```

2. Create virtual environment
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Quick Start
To anonymize a specific column (e.g., `NOTETXT`) in a CSV file:
```bash
python src/spo_clinical_note_deidentification.py
```

Update the script to call:
```python
process_notes_in_csv("path_to_your_file.csv", "NOTETXT", analyze_and_anonymize)
```

### Common Use Cases

#### Use Case 1: Anonymize clinical notes
```python
from src.spo_clinical_note_deidentification import process_notes_in_csv, analyze_and_anonymize

process_notes_in_csv("clinical_notes.csv", "NOTETXT", analyze_and_anonymize)
```

## Project Structure
```
clinical-note-deidentification/
├── src/
│   └── spo_clinical_note_deidentification.py    # Main script for deidentification using Presidio
├── LICENSE                                      # License information
├── README.md                                    # Project documentation
├── requirements.txt                             # Python dependencies
└── .gitignore                                   # Files to be ignored by Git
```

## Configuration

### Environment Variables
No environment variables are needed.

### Configuration Files
- `requirements.txt`: Lists all Python dependencies.
- Configuration is handled inside the script (`spo_clinical_note_deidentification.py`) including patterns and recognizers.

## Data Requirements

### Input Data Format
- CSV file with a text column (e.g., `NOTETXT`)
- Text data should be in plain English

### Output Data
- CSV file with the same name, updated in-place with deidentified text replacing the original column content



## Contributing
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Open a Pull Request

### Contribution Guidelines
- Use clear, descriptive commit messages
- Test before submitting
- Document any new functionality

## License
This project is licensed under the **Attribution Non-Commercial 4.0 International License** - see the [LICENSE](LICENSE) file for details.

Copyright (c) 2025 The General Hospital Corporation

## Acknowledgments
- [Presidio](https://github.com/microsoft/presidio) by Microsoft for PII detection and anonymization

## Contact
- **Project Maintainer**: Siril Raj Singa (*ssinga[at]mgh[dot]harvard[dot]edu*)
- **Issues**: [WIP]

---
**Last Updated**: August 10, 2025 | **Version**: 1.0.0
