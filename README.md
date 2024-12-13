# OBIO Company List

## Project Description
This project is a web scraper designed to extract company information from the EAHN (Enterprises Accelerating Health Network) company directory. The scraper collects detailed information about healthcare and biotech companies listed on eahn.obio.ca, including company descriptions, websites, and key features.

## Features
- Extracts company information from the main directory page
- Scrapes detailed information from individual company subpages
- Handles network errors with retry mechanism
- Implements rate limiting to avoid server overload
- Exports data to CSV format with Excel compatibility
- Progress tracking and detailed logging
- Configurable company limit for testing

## Requirements
- Python 3.7+
- Required packages:
  ```
  beautifulsoup4
  requests
  ```

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/OBIO_company_list.git
   cd OBIO_company_list
   ```

2. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
### Basic Usage
Run the script with default settings (10 companies):
```bash
python company_extractor.py
```

### Output
The script generates a CSV file (`eahn_companies.csv`) containing:
- Company name
- Company page URL
- Logo URL
- Company title/heading
- Description
- Website URL
- Key points/features

## Data Structure
The extracted data is organized in CSV format with the following columns:
```
name,url,logo_url,title,description,website,points
```

## Error Handling
- Implements retry mechanism for failed requests
- Continues processing if one company fails
- Detailed error logging for debugging
- Graceful handling of missing data fields

## Testing
Initial runs are limited to 10 companies for testing purposes. To process all companies, modify the `limit` parameter in `main()`:
```python
companies = extractor.process_companies(limit=None)  # Process all companies
```

## Project Structure
```
OBIO_company_list/
├── company_extractor.py  # Main script
├── requirements.txt      # Package dependencies
└── README.md            # Project documentation
```

## Best Practices
- Respect website's robots.txt
- Implement reasonable delays between requests
- Handle server responses appropriately
- Use proper user agent strings
- Implement error handling and logging

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments
- EAHN/OBIO for providing company information
- BeautifulSoup4 for HTML parsing capabilities
- Requests library for HTTP functionality