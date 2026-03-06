# Disaster Recovery

As your career progresses, you will encounter some kind of disaster. It may be a natural disaster, a cyber attack, or even a personal emergency. In this section, we will discuss how to prepare for and recover from disasters in the context of your career.

## Disaster Metrics (OB 3.3)

What is a disaster? Well imagine you go to work one day and find that the power went out or a flood has damaged your office or a cyber attack has compromised your company's data. These are all examples of disasters that can impact your career.

A lot of times disasters will lead to data loss, which can be catastrophic for a business. To measure the impact of a disaster, we use two key metrics: **Recovery Time Objective (RTO)** and **Recovery Point Objective (RPO)**.

### Recovery Point Objective (RPO)

**RPO** is the maximum acceptable amount of data loss **measured in time** before the disaster occurs. For example, if your RPO is 4 hours, it means that you can afford to lose up to 4 hours of data in the event of a disaster. If a disaster occurs and you lose more than 4 hours of data, you have exceeded your RPO.

It determines the **maximum age of files** that must be recovered from backup storage for normal operations to resume if a computer system or network goes down due to a disaster. RPO is a measure of how much data loss is acceptable in the event of a disaster.

For example, let's say you have a database that is backed up every 24 hours. If a disaster occurs and you lose the last 24 hours of data, your RPO is 24 hours. If you have a database that is backed up every hour, your RPO is 1 hour. Is it acceptable or not? That depends on the business requirements and the criticality of the data. If the data is critical and cannot be lost, then a lower RPO is required.

### Recovery Time Objective (RTO)

**RTO** is the maximum acceptable amount of time **measured in hours or days** that it takes to restore normal operations after a disaster occurs. For example, if your RTO is 24 hours, it means that you must be able to restore normal operations within 24 hours of a disaster occurring. If it takes longer than 24 hours to restore normal operations, you have exceeded your RTO.

RTO is a measure of how quickly you need to recover from a disaster to avoid significant impact on your business operations. It helps organizations plan their disaster recovery strategies and allocate resources effectively.

### Mean Time Between Failures (MTBF)

**MTBF** is a measure of how reliable a system or component is. It is the average time between failures of a system or component. For example, if a system has an MTBF of 1000 hours, it means that on average, the system will fail once every 1000 hours of operation.

A higher MTBF indicates a more reliable system, while a lower MTBF indicates a less reliable system. MTBF is an important metric for disaster recovery planning, as it helps organizations understand the likelihood of system failures and plan accordingly.

### Mean Time to Repair (MTTR)

**MTTR** is a measure of how quickly a system or component can be repaired after a failure. It is the average time it takes to repair a system or component after a failure occurs. For example, if a system has an MTTR of 2 hours, it means that on average, it will take 2 hours to repair the system after a failure.

A lower MTTR indicates a more efficient repair process, while a higher MTTR indicates a slower repair process. MTTR is an important metric for disaster recovery planning, as it helps organizations understand the time required to restore normal operations and plan accordingly.

## Recovery Sites (OB 3.3)

When a disaster occurs, it may not be possible to continue operations at the primary site. In such cases, organizations may need to use a recovery site to continue operations. There are three types of recovery sites: hot sites, warm sites, and cold sites.

**Cold Sites**: Cold sites are the most affordable option for disaster recovery. They are essentially empty data centers that are equipped with the necessary infrastructure (power, cooling, networking) but do not have any pre-installed hardware or software. In the event of a disaster, organizations can move their operations to a cold site and set up their systems from scratch. However, this can take a significant amount of time and may result in extended downtime.

- Contains no pre-installed hardware or software
- Requires significant time to set up and restore operations sometimes taking days or weeks
- Most affordable option for disaster recovery

**Warm Sites**: Warm sites are a step up from cold sites. They have some pre-installed hardware and software, but not all of the necessary components to run operations. In the event of a disaster, organizations can move their operations to a warm site and set up their systems more quickly than at a cold site. However, there may still be some downtime while systems are configured and data is restored.

- Contains some pre-installed hardware and software and out of date configurations
- Requires less time to set up and restore operations than a cold site, but still may take hours or days
- More expensive than a cold site, but less expensive than a hot site

**Hot Sites**: Hot sites are the most expensive option for disaster recovery. They are fully equipped data centers that have all the necessary hardware, software, and configurations to run operations. In the event of a disaster, organizations can move their operations to a hot site and resume operations almost immediately. However, hot sites require significant investment and ongoing maintenance.

- Fully equipped with all necessary hardware, software, and configurations
- Requires minimal time to set up and restore operations, often within minutes or hours
- Most expensive option for disaster recovery
