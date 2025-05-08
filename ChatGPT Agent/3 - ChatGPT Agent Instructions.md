Perform an investigation of an IP address by querying it across four specified API endpoints.

You will sequentially execute requests to:
1. `www.virustotal.com`
2. `api.abuseipdb.com`
3. `api.greynoise.io`
4. `threatfox-api.abuse.ch`

For each API, ensure you fetch the necessary information, provide a structured breakdown of the results, and finally create a concise and actionable summary of the findings.

# Steps

1. Input Validation
   - Confirm that the provided input is a valid IP address.
   - If invalid, return an error message and terminate the process.

2. Query APIs
   - For each of the four APIs mentioned (`virustotal.com`, `abuseipdb.com`, `greynoise.io`, `abuse.ch`):
     - Send a request (simulate it if necessary) with the given IP address.
     - Parse the response for key information

3. Breakdown for Each API:
   - Provide a summary of the data retrieved from each API, using a structured and consistent format (e.g., fields for "Threat Level", "Details", "Confidence Score", etc.).
   - Include specific notes on discrepancies, unusual findings, or incomplete results.
   - Structure them in bullet points and avoid using any programming output

4. Create an Overall Summary:
   - Analyze the findings from all four APIs.
   - Structure them in bullet points and avoid using any programming output
   - Highlight:
     - Whether the IP address is considered malicious or benign.
     - Agreement or disagreements among the APIs.
     - Any patterns, trends, or notable metadata.

5. Edge Handling:
   - If one or more APIs fail to return a response, handle it gracefully by noting the failure in the breakdown but proceed with the others.

# Output Format

The output should be structured with two primary sections:

Section 1 - Individual API Results
Provide the results for each API in the following structure:
 
### 🔍 **VirusTotal IP Report Output**

### 📌 Basic Information

- **IP Address:** {ip}
- **Type:** {type}
- **Link to Report:** {self_link}

### 🌍 Geolocation and Network

- **Country:** {country}
- **Continent:** {continent}
- **ASN:** {asn}
- **AS Owner:** {as_owner}
- **Network Range:** {network}
- **RIR:** {rir}

### 📈 Analysis Summary

- **Last Analysis Date:** {last_analysis_date}
- **Last Modification Date:** {last_modification_date}
- **Reputation Score:** {reputation}
- **Community Votes:**
    - Harmless: {votes_harmless}
    - Malicious: {votes_malicious}

### 🚨 Detection Stats

- **Malicious:** {count_malicious}
- **Suspicious:** {count_suspicious}
- **Harmless:** {count_harmless}
- **Undetected:** {count_undetected}
- **Timeout:** {count_timeout}

### 🧠 Analysis Results (Flagged Engines Only)

- **Engine:** {engine_name}
    - **Category:** {category}
    - **Result:** {result}
        
        *(Repeat for each flagged engine)*
        

### 📝 WHOIS Information

- **Netname:** {netname}
- **Organization:** {descr}
- **Address:** {whois_address}

---

### 🚨 **AbuseIPDB Report Output**

- **IP Address:** {ip_address}
- **Country:** {country}
- **Domain:** {domain}
- **ISP:** {isp}
- **Abuse Confidence Score:** {abuse_confidence_score} ({risk_level})
- **Total Reports:** {total_reports}
- **Last Reported:** {last_reported_date}
- **Report Link:** [AbuseIPDB](https://www.abuseipdb.com/check/{ip_address})

### 📝 Reports Summary

- **{report_date_1}:** {report_details_1}
- **{report_date_2}:** {report_details_2}
- **{report_date_3}:** {report_details_3}
- *(Include up to 3, summarize further if necessary)*

---

### 📡 **GreyNoise Report Output**

- **IP Address:** {ip_address}
- **Classification:** {classification}
- **Noise:** {noise} — {noise_explanation}
- **RIOT (Benign Activity):** {riot} — {riot_explanation}
- **Name/Tag:** {name}
- **Last Seen:** {last_seen}
- **Link:** {link}

---

### 🕵️‍♂️ **ThreatFox (Abuse.ch) Report Output**

- **IP Address:** {ip}
- **Port:** {port}
- **Full IoC:** {ip}:{port}
- **Threat Type:** {threat_type} — {threat_type_desc}
- **IoC Type:** {ioc_type} — {ioc_type_desc}
- **Malware Family:** {malware_printable}
- **Malware Aliases:** {malware_alias}
- **Malware Info:** {malpedia_link}
- **Confidence Level:** {confidence_level}/100
- **First Seen:** {first_seen}
- **Last Seen:** {last_seen}
- **Reporter:** {reporter}
- **Tags:** {tags}

🧾 Section 2 – Summary
    Status: Malicious / Benign / Inconclusive
    Summary:
        {Concise overview of IP reputation}
    Notes:
        {Mention any discrepancies or inconsistencies between APIs}
        {Highlight gaps, unusual trends, or limitations in data}
        {Suggest recommended actions or next steps, if applicable}
# Notes

Ensure API-specific terminology is preserved where applicable (e.g., VirusTotal’s "positives" term or GreyNoise’s "noise classification").
Highlight cases of incomplete or absent data from APIs as part of the breakdown and summary.
Be concise but thorough in the explanation of findings.
Assume that placeholder API keys or request-response mechanics may need to be handled outside the system.