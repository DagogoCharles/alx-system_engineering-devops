
Postmortem: Web Stack Outage Incident
 
Issue Summary:
Duration: June 1, 2023, 10:00 AM - June 1, 2023, 2:00 PM (PST)
Impact: Service outage for the Customer Support Portal
User Experience: Users were unable to access the Customer Support Portal, resulting in a complete loss of functionality. Approximately 75% of users were affected during the outage period.
 
Root Cause:
The root cause of the web stack outage was identified as a database connection issue. Due to a misconfiguration in the database connection pool settings, the application servers were unable to establish connections with the database, leading to a complete failure of the Customer Support Portal.
 
Timeline:
10:00 AM: The issue was initially detected when an engineer noticed a spike in error logs related to database connectivity.
10:05 AM: The monitoring system sent out an alert indicating high error rates on the application servers.
10:10 AM: The incident response team was assembled, and investigations began to identify the cause of the issue.
10:30 AM: Initial assumptions pointed towards a network connectivity problem. Network logs were analysed and network teams were engaged.
11:00 AM: Network investigations did not reveal any issues, and attention shifted towards the application layer.
11:30 AM: After analysing the application logs and server configurations, it was suspected that the database connection pool settings might be misconfigured.
12:00 PM: The incident was escalated to the database administration team for further investigation and resolution.
1:00 PM: The root cause was confirmed as a misconfiguration in the database connection pool settings, leading to exhausted connections and subsequent service failure.
1:30 PM: The incident was resolved by adjusting the database connection pool settings to accommodate the expected workload and increasing the maximum number of connections allowed.
2:00 PM: The Customer Support Portal was fully restored, and normal functionality resumed.
Root Cause and Resolution:
The issue was caused by a misconfiguration in the database connection pool settings. The existing configuration did not account for the increasing user load on the Customer Support Portal, resulting in all available connections being exhausted. As a result, the application servers were unable to establish new connections with the database, causing the service outage.
 
To resolve the issue, the database connection pool settings were adjusted. The maximum number of connections allowed was increased to accommodate the expected workload, ensuring sufficient capacity for concurrent connections. After applying the configuration changes, the Customer Support Portal regained connectivity with the database, and the service was fully restored.
 
Corrective and Preventative Measures:
Improve monitoring: Enhance the monitoring system to provide real-time visibility into database connection usage, enabling early detection of potential issues.
Load testing and capacity planning: Conduct regular load testing exercises to ensure that the database connection pool settings are properly configured to handle anticipated user loads.
Automation and configuration management: Implement automation for the deployment and configuration of the database connection pool settings to reduce the risk of human error during setup.
Documentation and knowledge sharing: Document the incident, including the root cause analysis and resolution steps, to enhance the knowledge base and facilitate faster troubleshooting in the future.
Incident response training: Conduct training sessions with the incident response team to improve their ability to quickly identify and resolve similar issues in the future.
Tasks to Address the Issue:
Update the monitoring system to include database connection usage metrics.
Perform regular load testing to validate the scalability of the database connection pool.
Implement automated configuration management for the database connection pool settings.
Document the incident, including the root cause analysis and resolution steps.
Conduct incident response training sessions to enhance the team's skills and knowledge.
By implementing these measures, we aim to prevent similar incidents in the future and ensure a more resilient and reliable Customer Support Portal.


