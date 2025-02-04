# Building-a-SIEM

## Objective

We will build a SIEM system using Elastic Security, focusing on real-time threat detection and malware analysis. This involves setting up the Elastic Stack (Elasticsearch, Kibana, and optional Logstash) and deploying Elastic Agents on endpoints to collect security logs. We will configure detection rules to identify malware and suspicious activity, using Kibana dashboards for monitoring and analysis. To ensure effectiveness, we will simulate attacks and refine detection rules for accuracy. The goal is to create a proactive security monitoring solution that enhances threat detection and response capabilities.

### Skills Learned

- Skill 1
- Skill 2

### Tools Used

- List the tools and what you did with it.

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


