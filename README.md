# Computer-Application-and-Security-Task-Part-4

# Network Scanning Guide using fping, nbtscan, and Nmap

This guide provides step-by-step instructions for performing network scanning using fping, nbtscan, and Nmap tools within a Kali Linux environment.

## 1. Identifying Alive Systems with fping

1. **Scan for Alive Systems:**
   - Open a terminal in Kali Linux.
   - Use the following command to identify systems that are alive on the network:
     ```
     fping -a -s -g 192.168.56.101/24
     ```
   This command pings all IP addresses within the specified range (`192.168.56.101/24`) and shows the systems that respond.

## 2. Confirming IP Address with nbtscan

1. **Using nbtscan:**
   - Once you have identified the alive IP addresses from the previous step, use the nbtscan tool to confirm the correct IP address of your Metasploitable2 VM.
   - Run the nbtscan tool on each of the alive IP addresses to identify the target system:
     ```
     nbtscan <alive_IP_address>
     ```

## 3. Performing Nmap Scan

1. **Nmap Scan with TCP SYN, OS Detection, and Version Detection:**
   - Again from within your Kali Linux VM, perform a single Nmap scan with the following options:
     - TCP SYN scan (`-sS`): Stealthy scan technique to determine open ports.
     - OS detection (`-O`): Attempts to determine the operating system of the target.
     - Version detection (`-sV`): Attempts to determine service and application versions running on open ports.
     - Verbose output (`-v`): Provides detailed output during the scan.
   - Use the following command:
     ```
     nmap -sS -O -sV -v <target_IP>
     ```
   Replace `<target_IP>` with the IP address of the system you want to scan.

## Disclaimer

This guide is for educational purposes only. Ensure that you have proper authorization before performing any network scanning activities.
