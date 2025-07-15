# DNS Log Analysis using Splunk SIEM

## Description
This project showcases the ingestion and analysis of DNS log files utilizing **Splunk SIEM**. The primary focus is on extracting actionable insights from DNS traffic to identify potential threats and anomalies. This project marked my initial hands-on experience with Splunk, undertaken by following a comprehensive YouTube course by [@0xrajneesh](https://www.youtube.com/@0xrajneesh).

## Objectives
* Upload and parse sample DNS log files into Splunk.
* Extract critical fields such as source IP, destination IP, domain name, query type, and response code.
* Utilize SPL (Search Processing Language) to detect anomalies and identify suspicious domains.
* Apply regex filters and statistical functions to analyze DNS traffic behavior.

## Prerequisites
* A functional Splunk instance, properly installed and configured.
* Sample DNS log files (plain text format) containing relevant DNS events.
* A basic understanding of Splunk Search Processing Language (SPL).

## Data Ingestion Steps

### 1. Prepare DNS Log Files
Ensure your log files include essential fields such as source IP, Fully Qualified Domain Name (FQDN), query type, and response code.

### 2. Upload Logs to Splunk
Navigate to `Settings > Add Data > Upload` and select your DNS log file(s).

### 3. Set Source Type
Assign an appropriate source type (e.g., `dns_sample`). Configure the correct index and host for the ingested data.

### 4. Verify Ingestion
Confirm successful data ingestion by executing a basic search:
```splunk
index=<your_dns_index> sourcetype=dns_sample
```

## 🔍 DNS Log Analysis in Splunk

### 1. Basic DNS Event Search
```spl
index=* sourcetype=dns_sample
```

### 2. Filter DNS-Related Events with Regex
```spl
index=* sourcetype=dns_sample | regex _raw="(?i)\b(dns|domain|query|response|port 53)\b"
```

### 3. Identify Traffic Spikes by Domain
```spl
index=* sourcetype=dns_sample | stats count by fqdn
```

### 4. Top Sources by Domain Queries
```spl
index=* sourcetype=dns_sample | top fqdn, src_ip
```

### 5. Investigate Known Malicious Domains
```spl
index=* sourcetype=dns_sample fqdn="maliciousdomain.com"
```

## 📈 Outcome

  - Successfully identified high-traffic DNS domains.

  - Detected anomalies and abnormal patterns in DNS activity.

  - Built a strong foundational understanding of using Splunk for security log analysis.

  - Laid the groundwork for future projects in threat detection and security operations.
