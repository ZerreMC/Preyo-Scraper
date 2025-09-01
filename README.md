# Preyo-Scrapper
A dynamic web scraping framework for Spanish supermarkets including Mercadona, Lidl, Aldi, Dia, Bonpreu, and Condis.

## 📋 Requirements
- Python 3.10+
- Docker (optional)
- WSL2 (for Windows users)

## 🛠️ Quick Start
### 1. Local Development Setup
```bash
# Clone repository
git clone <your-repo-url>
cd Preyo-Scrapper

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/WSL
# or
venv\Scripts\activate   # Windows

# Install dependencies
pip install -r config/requirements.txt

# Install Playwright browsers
playwright install chromium

# If get any advice after install chromium
playwright install-deps
```

## 🎯 Usage
### Run Specific Spider
```bash
# Local execution
PYTHONPATH=src scrapy crawl mercadona -a postal_code=28001

# Docker execution
make docker-run-data
```

## 📊 Data Output
Scraped data is saved in Parquet format in the `./data` directory with the following structure:
- **supermarket**: Store name (e.g., "Mercadona")
- **category**: Product category
- **name**: Product name
- **price**: Product price (float)
- **postal_code**: Location code
- **scraped_at**: Timestamp

## 🏗️ Project Structure
```
Preyo-Scrapper/
├── config/              # Configuration files
│   ├── requirements.txt
│   ├── environment.yml
│   └── proxies.txt
├── src/
│   ├── core/           # Base classes
│   ├── interfaces/     # Execution interfaces
│   ├── supermarkets/   # Spider implementations
│   └── utils/          # Utilities
├── data/               # Output directory
├── docker-compose.yml
├── Dockerfile
└── Makefile
```

## ⚠️ Legal Considerations
- Respect robots.txt when appropriate
- Implement reasonable delays between requests
- Don't overload target servers
- Use scraped data responsibly

## 🤝 Contributing
1. Fork the project
2. Create feature branch (`git checkout -b feature/new-feature`)
3. Commit changes (`git commit -am 'Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Create Pull Request

## 📝 License
This project is licensed under the 
[Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/),
with **additional author terms**.

You are free to:
- **Share** — copy and redistribute for educational and research purposes  
- **Adapt** — remix, transform, and build upon for non-commercial purposes  

Under the following terms:
- **Attribution** — You must credit:  
  **Sebastian J. Gutierrez Llorca (GitHub: [ZerreMC](https://github.com/ZerreMC))**  
- **NonCommercial** — You may not use this software or its derivatives for 
  commercial purposes.  

⚠️ **Exclusive Monetization Rights**:  
Only the author may monetize this software. Commercial use, integration into 
paid applications, or providing paid services with this software is strictly prohibited.
