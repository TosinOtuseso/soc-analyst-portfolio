#  MITRE ATT&CK Mapping – SOC138 Incident

##  Attack Flow

1. Phishing email delivers XLS file
2. User opens file (“Accessed”)
3. Macro executes malicious payload
4. PowerShell script runs
5. External C2 communication begins
6. Security system flags file as malicious
7. File not quarantined automatically

---

##  Techniques Identified

| Tactic | Technique | ID | Explanation |
|--------|----------|----|-------------|
| Initial Access | Phishing Attachment | T1566.001 | Malicious XLS delivered via email |
| Execution | User Execution | T1204 | User opened file |
| Execution | PowerShell | T1059.001 | Script execution observed |
| Defense Evasion | Obfuscation | T1027 | Macro/encoded payload |
| Command & Control | Application Layer Protocol | T1071 | HTTPS traffic used |

---

##  Key Insight

This attack demonstrates a **multi-stage execution chain typical of Office macro malware campaigns.**
