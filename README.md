# CNPJ.API

![Project Banner](https://socialify.git.ci/fepaziani/CNPJ.API/image?description=1&language=1&name=1&owner=1&pattern=Solid&stargazers=1&theme=Dark)

## 📌 Overview
CNPJ.API is a **FastAPI** application that queries CNPJ data from the **ReceitaWS API** for a list of CNPJs stored in an Excel file. It implements **rate limiting** (3 requests per minute) and **caches results** to avoid redundant API calls. The updated Excel file includes a new column with the fetched CNPJ data.

## 🚀 Features
- **FastAPI-based** backend for querying CNPJ data.
- **ReceitaWS API integration** to fetch CNPJ details.
- **Rate limiting** (3 requests per minute) to comply with API restrictions.
- **In-memory caching** to optimize performance and avoid redundant queries.
- **Excel processing**: Reads a column of CNPJs and updates the file with fetched data.

## 🛠 Tech Stack
- **Backend**: FastAPI, Uvicorn
- **Data Processing**: Pandas, OpenPyXL
- **API Requests**: Requests library
- **Rate Limiting & Caching**: Python defaultdict

## 📂 Project Structure
```
CNPJ.api-main/
│-- code/                 # Source code
│-- README.md             # Project documentation
│-- .gitignore            # Git ignore file
|-- requirements.txt      # Required Modules to Run the Program
```

## 🚀 Getting Started
### 1️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```
### 2️⃣ Run the FastAPI Server
```
uvicorn code:app --host 0.0.0.0 --port 8000
```
### 3️⃣ Query CNPJs from an Excel File
```
curl -X 'POST' \
  'http://127.0.0.1:8000/query_cnpjs_from_excel/' \
  -H 'Content-Type: application/json' \
  -d '{"file_path": "path/to/your/excel.xlsx"}'
```

## 📌 Example
### 📝 Input (Excel File - Column 'CNPJ')
```
CNPJ
12345678000195
98765432000199
...
```
### 🔄 Processing
For each CNPJ, the API returns structured data like:
```
{
  "nome": "Company A",
  "endereco": "Street XYZ, 123",
  "situacao": "ATIVA"
}
```
### ✅ Output (Excel File - Updated with CNPJ Data)
```
| CNPJ            | CNPJ Data                                            |
|----------------|------------------------------------------------------|
| 12345678000195 | `{"nome": "Company A", "endereco": "Street XYZ, 123"}` |
| 98765432000199 | `{"nome": "Company B", "endereco": "Avenue ABC, 456"}` |
...
```

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## 📜 License

This project is licensed under the MIT License.

## 📊 Project Stats

![GitHub Repo stars](https://img.shields.io/github/stars/fepaziani/CNPJ.API.Data?style=social)
![GitHub forks](https://img.shields.io/github/forks/fepaziani/CNPJ.API?style=social)
![GitHub issues](https://img.shields.io/github/issues/fepaziani/CNPJ.API)
![GitHub last commit](https://img.shields.io/github/last-commit/fepaziani/CNPJ.API)

---

*Developed by fepaziani*
