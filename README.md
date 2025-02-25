# Building-a-SIEM

## Objective

We will build a SIEM system using Elastic Security, focusing on real-time threat detection and malware analysis. This involves setting up the Elastic Stack (Elasticsearch, Kibana, and optional Logstash) and deploying Elastic Agents on endpoints to collect security logs. We will configure detection rules to identify malware and suspicious activity, using Kibana dashboards for monitoring and analysis. To ensure effectiveness, we will simulate attacks and refine detection rules for accuracy. The goal is to create a proactive security monitoring solution that enhances threat detection and response capabilities.

### **Skills Learned**  
- Configuring and managing **Elastic Security SIEM** for real-time threat detection.  
- Deploying and managing **Elastic Agents** to collect and analyze security logs.  
- Writing and tuning **detection rules** to identify malware and suspicious activities.  
- Using **Kibana dashboards** for security monitoring and visualization.  
- Simulating **malware attacks** and refining threat detection strategies.  

### **Tools Used**  
- **Elastic Stack (Elasticsearch, Kibana, Logstash)** – Set up and configured the SIEM environment for log collection and security analysis.  
- **Elastic Agent** – Installed and deployed on endpoints to collect system logs and detect threats.  
- **Kibana** – Used to visualize data, analyze security logs, and monitor system activity.  
- **Detection Rules & Machine Learning Jobs** – Implemented to automatically identify malware and suspicious behavior.  
- **Windows Event Logs** – Integrated into Elastic Security for host-based monitoring.  


## Steps

These are the steps to create a tool to monitor attacks.

### 1.Setting up our SIEM
<p>
    We will need to first create an account on Elastic.co
</p>
<div>
  <a href="https://www.elastic.co/downloads/" target="_blank">
    <img src="https://img.shields.io/badge/Download-Elastic%20Stack-blue?logo=elastic&logoColor=white" alt="Download Elastic Stack" />
  </a>
</div>

<div>
<a href="https://postimg.cc/ZBDjpV1D"> 
    <p>We need to choose Elastic for Security as we're using it for security purposes.</p>
</a>
</div>

<p>The provider will be AWS as we cannot pick another one.</p>

### 2.Exploring the Elastic SIEM
<div>
<a href="https://postimg.cc/nCQTQ8py"> 
    <p>Our SIEM is now successfully created!</p>
</a>
</div>

<p>We can use dashboards to see alerts when the logs are ingested.</p>

<p>There will be a rules tab to detect malicious activity.</p>

<div>
<a href="https://postimg.cc/pyxtCt0t"> 
    <p>These are the rules</p>
</a>
</div>

<p>There's a query that looks for that particular entry in the log.</p>

<div>
<a href="https://postimg.cc/fk2DRrKn"> 
    <p>Anything that is detected will be shown here.</p>
</a>
</div>

<p>You can explore the rest on your own.</p>

### 3.Installing the Agents
<p>Let's now ingest data into the Elastic SIEM. This will help us generate alerts and detect suspicious activity.</p>

<p>But before we start we must install our Windows 11 Virtual Machine.</p>

<a href="https://www.microsoft.com/en-us/evalcenter/download-windows-11-enterprise" target="_blank">
    <img src="https://img.shields.io/badge/Download-Windows%2010%20Enterprise-blue?logo=windows&logoColor=white" alt="Download Windows 11 Enterprise" />
</a>

<p>You can use VMware or VirtualBox to set up Windows 11.</p>

<p>Make sure you set the machine up.</p>

<div>
<a href="https://postimg.cc/rzMB0Zwq"> 
    <p>The Virtual Machine will look like this.</p>
</a>
</div>

<p>We can add our agent on fleet page of the assets tab.</p>

<div>
<a href="https://postimg.cc/BXWTz48M"> 
    <p>This is the fleet tab to add our agent.</p>
</a>
</div>

<div>
    <a href="https://postimg.cc/r0nmDKwG"> 
    <p>We will add our agent by copying and pasting the code to the Windows VM.</p>
</div>

<p>Now we are in the VM we need to add a command before pasting the code.</p>

<p>Make sure to open Windows Powershell and run it as an Administrator.</p>

<div>
    <a href="https://postimg.cc/dZ9vCgzy"> 
    <p>Set-ExecutionPolicy RemoteSigned -Scope Process</p>
</div>

<p>This command allows powershell to run locally created scripts without any signature. The -Scope Process makes sure this change applies only to the current session and resets once the powershell is closed. This is great as it helps us run scripts safely without permanantly modifying system-wide execution policies.</p>

<p> we need to now copy and paste the code to the powershell.</p>

<div>
    <a href="https://postimg.cc/vDDRmDzG"> 
    <p>The code we found when creating the fleet.</p>
</div>

<p>You just need the message saying the Elastic Agent has been installed successfully.</p>

<div>
    <a href="https://postimg.cc/Yv8K9FJq"> 
    <p>This is the message you'll get when you finished installing the Elastic Agent when creating the fleet.</p>
</div>

<div>
    <a href="https://postimg.cc/68HZhHks"> 
    <p>The fleet overview confirming it's installed.</p>
</div>

<p>Now that we successfully made our agent. Lets move onto the integrations side.</p>

### 4.Setting up the integrations

<p>We will now make the integrations adding to the agent so it can make detections. These can be found on the assets tab.</p>

<div>
    <a href="https://postimg.cc/bDQLrFFZ"> 
    <p>The integration we will be adding.</p>
</div>

<p>Setting the integration is easy you just need to add it into the Agent Policy.</p>

<div>
    <a href="https://postimg.cc/SYWgJQDF"> 
    <p>The integration we will be adding.</p>
</div>

<p>You just need to add the Windows log and the system logs now.</p>

<div>
    <a href="https://postimg.cc/tYLpPBqX"> 
    <p>The dashboards now.</p>
</div>

<p>We now see there are results on the dashboards now.</p>

<div>
    <a href="https://postimg.cc/k2fszp2C"> 
    <p>The different dashboards you can see.</p>
</div>

<div>
    <a href="https://postimg.cc/ZWM70Q4c"> 
    <p>The new rule we created.</p>
</div>

<p>We will now go back to our Windows 11 VM and type in more commands.</p>

<div>
    <a href="https://postimg.cc/nCYK6PXz"> 
    <p>Set-NetFirewallProfile -All -Enabled True</p>
</div>

### Conclusion 

<p>We successfully learned how to setup Elastic SIEM. Install agents and learn how the SIEM can generate alerts.</p>

<p>We learned how to blue team engineer the SIEM and how analysts actually get alerts.</p>

