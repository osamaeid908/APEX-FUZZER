````markdown
╔═══════════════════════════════════════════════╗
               APEX-FUZZER v1.0              
         Advanced API Endpoint Discovery       
                                             
           Developed by: Osama Eid          
╚═══════════════════════════════════════════════╝

APEX-FUZZER is a powerful, automated API endpoint discovery tool designed for penetration testers, bug hunters, and security researchers.  
It performs intelligent fuzzing on API endpoints to identify valid, hidden, and unusual API paths using customizable requests, rate limiting, retry logic, and detailed result summaries.

---

## 🚀 Features

- ✔️ Automatic API endpoint fuzzing  
- ✔️ Supports both local wordlists and remote SecLists  
- ✔️ Rate limit control (`--rate-limit`)  
- ✔️ Retry mechanism for unstable servers  
- ✔️ Custom request headers (JSON format)  
- ✔️ Timeout control for slow targets  
- ✔️ Saves discovered endpoints to a file  
- ✔️ Color-coded terminal output for easy analysis  
- ✔️ Detailed summary (status codes, failures, retries, unusual responses)

---

## 📦 Installation

```bash
git clone <YOUR_REPO_URL>
cd APEX-FUZZER
pip install -r requirements.txt
````

Or manually install dependencies:

```bash
pip install requests colorama
```

---

## 🛠 Usage

### **Basic Usage**

```bash
python api_fuzzer.py https://example.com/
```

### **Use Custom Wordlist**

```bash
python api_fuzzer.py https://example.com/ --wordlist wordlist.txt
```

If no wordlist is provided, the tool automatically downloads:

```
SecLists/Discovery/Web-Content/common.txt
```

### **Set Rate Limit (requests per second)**

```bash
python api_fuzzer.py https://example.com/ --rate-limit 5
```

### **Add Custom Headers**

```bash
python api_fuzzer.py https://api.example.com/ --headers '{"Authorization": "Bearer TOKEN"}'
```

### **Set Request Timeout**

```bash
python api_fuzzer.py https://example.com/ --timeout 15
```

### **Save Results to a File**

```bash
python api_fuzzer.py https://example.com/ --output results.txt
```

### **Quick Save (default: `discovered_endpoints.txt`)**

```bash
python api_fuzzer.py https://example.com/ -o
```

---

## 📊 Output Example

* **Valid Endpoint (200)**
* **Unusual Response (403 / 500 / 302 etc.)**
* **Invalid Endpoint (404)**

The tool also prints a summary containing:

* Total requests
* Failed requests
* Retry count
* Status code statistics
* List of valid endpoints
* Unusual endpoints with codes

---

## 📁 Project Structure

```
api_fuzzer.py       → Main tool
wordlists/          → (optional) Your custom lists
README.md           → Documentation
```

---

## 🧠 How It Works (Internal Logic)

1. Loads a local wordlist or downloads one automatically
2. Iterates through all words and appends them to the base URL
3. Sends HTTP requests using a session with retry logic
4. Classifies responses into:

   * **Valid endpoints (200)**
   * **Unusual but interesting (all non-404 except 200)**
   * **Invalid (404)**
5. Displays results and optionally saves them to a file

---

## ⚠️ Legal Disclaimer

APEX-FUZZER is intended **only for legal security testing**, educational purposes, and authorized penetration testing.
The developer **Osama Eid** is not responsible for any misuse.

---

## 👨‍💻 Developer

**Osama Eid**
Advanced Security Research Tools

---

## ⭐ Support the Project

If you like this tool, consider giving the repository a star ⭐ and contributing improvements!

---

```

---

If you want, I can also:  
✅ Create a logo/banner for the project  
✅ Generate a setup.py or pip package format  
✅ Build a GitHub release description 

Just tell me!
```
