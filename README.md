

# Monitor Oracle Cloud Infrastructure with Datadog

## Introduction

The Oracle Cloud  [Observability and Manageability platform](https://blogs.oracle.com/cloud-infrastructure/announcing-the-oracle-cloud-observability-and-management-platform)  aims to meet our customers where they are. We understand that they have standardized their operational postures with popular 3rd party Observability tools and we want to be interoperable with those tools so our customers can continue using the tools they have invested in with Oracle Cloud Infrastructure.

In this tutorial, we will walk you through how you can move logs from Oracle Cloud Infrastructure into  [Datadog](https://www.sumologic.com/). Datadog is a popular Observability tool that provides monitoring and security services that provide full visibility into your applications.

Our solution architecture at high level is as shown below
![enter image description here](https://github.com/mayur-oci/sumologic/blob/main/sl_archi.png?raw=true)

## Create a Custom HTTP Source Collector in Sumologic

In Sumologic account, you need to create [HTTP custom collector app](https://help.sumologic.com/03Send-Data/Sources/02Sources-for-Hosted-Collectors/HTTP-Source) as described in the steps below.

1. Click on the  *Setup Wizard* as shown below
![enter image description here](https://github.com/mayur-oci/sumologic/blob/main/1sl.png?raw=true)

2. Click on the option of *Start streaming data to Sumo Logic* as shown below
![enter image description here](https://github.com/mayur-oci/sumologic/blob/main/2sl.png?raw=true)

3. Click on the option *Your custom app* as shown below
![enter image description here](https://github.com/mayur-oci/sumologic/blob/main/3sl.png?raw=true)

4. Click on the option *HTTPS Source*
![enter image description here](https://github.com/mayur-oci/sumologic/blob/main/4sl.png?raw=true)

5. Configure your *HTTP Source* as shown below. Note *Source Category* is custom and depends on your application needs. It is a metadata tag, stored with your logs and is usefull when searching logs later in *Sumologic*, one ingested. Loglines we  are going to start with timestamps, hence we also choose the option *Use time zone from log file*.
![enter image description here](https://github.com/mayur-oci/sumologic/blob/main/6sl.png?raw=true)

6. As you move to the next screen, we get the HTTPS endpoint for our logs to upload from OCI, using *POST* HTTP call, as shown below. 
![enter image description here](https://github.com/mayur-oci/sumologic/blob/main/8sl.png?raw=true)

## Configure the logs you want to capture

1. In the Oracle Cloud Infrastructure console, click the Navigation menu, select **Log Groups** under the **Logging** menu.

2. To create a log group, click  **Create Log Group**.
