<div style="
    max-width: 800px;
    margin: 40px auto;
    padding: 40px;
    background: white;
    box-shadow: 0 0 20px rgba(0,0,0,0.1);
    border-radius: 10px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
">

<!-- PDF Download Button -->
<div style="text-align:center; margin-bottom: 30px;">
  <a href="https://github.com/YOUR-USERNAME/YOUR-REPO/raw/main/resume.pdf" 
     download
     style="
       background-color: #007bff;
       color: white;
       padding: 12px 24px;
       border-radius: 6px;
       text-decoration: none;
       font-weight: bold;
       font-size: 16px;
     ">
    Download PDF
  </a>
</div>

<!-- Header Table -->
<table width="100%">
  <tr>
    <td align="left" width="70%">
      
# Atahar Hossain  
**Cyber Security Specialist**  

34 no. plot, East Ferozsha Colony, Ferozsha – 4207, Khulshi, Chattogram, Bangladesh  
📞 +88 01783970253  
✉️ atahar8080@gmail.com  
[LinkedIn Profile](https://www.linkedin.com/in/ataharhossain/)

</td>
    <td align="right" width="30%">
      <img src="https://github.com/Atahar08/My-reswume/blob/main/Gemini_Generated_Image_ticmceticmceticm.png?raw=true?raw=true" 
           alt="Atahar Hossain" width="180"/>
    </td>
  </tr>
</table>

---

## Summary  
Cybersecurity enthusiast with hands-on experience in vulnerability assessment, penetration testing, and cloud security. Skilled in Wireshark, Nmap, Kali Linux, and machine learning applications in security. Completed a Digital Marketing Internship, gaining expertise in data privacy, web systems, and anomaly detection. Proficient in creating reports and presentations to communicate complex concepts effectively.

---

## Skills  
- Cyber Security  
- Digital Marketing  
- Canva  
- Microsoft Word & PowerPoint  

---

## Experience  

### Digital Marketing Intern – Brain Machine  
*April 2025 – September 2025*  
- Ensured data privacy and compliance while handling user data, building strong awareness of security best practices (GDPR/CCPA).  
- Worked with web platforms, CMS, and analytics tools, gaining technical exposure to systems that are common security targets.  
- Conducted data analysis to identify trends and anomalies, and developed insights into how social engineering tactics parallel phishing and cyber threats.  

**Key Skills Gained:**  
- Data Privacy & Security Awareness  
- Web & System Exposure  
- Log/Anomaly Analysis  
- Understanding of Social Engineering  
- Technical Documentation  

---

## Certifications  
- Google Cyber Security Professional Certificate  
- EC Council Android Bug Bounty Hunting  

---

## Education  
**University of Science and Technology Chittagong**  
BSc in Computer Science & Engineering  
*January 2022 – Present*  

---

## Extracurricular Activities  
- Assistant Treasurer, Cultural & Sports Club, FSET (Faculty of Science Engineering & Technology), University of Science & Technology Chittagong  

</div>

---

### ✅ How to set up automatic PDF generation:

1. **Create GitHub Action:**  

Create a folder `.github/workflows/` in your repo and add a file `generate_pdf.yml`:

```yaml
name: Generate Resume PDF

on:
  push:
    branches:
      - main  # or your default branch

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Set up Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'

    - name: Install dependencies
      run: |
        npm install -g markdown-pdf

    - name: Convert README to PDF
      run: |
        markdown-pdf README.md -o resume.pdf

    - name: Commit PDF
      run: |
        git config --global user.name "github-actions[bot]"
        git config --global user.email "github-actions[bot]@users.noreply.github.com"
        git add resume.pdf
        git commit -m "Update resume PDF [skip ci]" || echo "No changes to commit"
        git push
