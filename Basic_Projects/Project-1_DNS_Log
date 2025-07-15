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
