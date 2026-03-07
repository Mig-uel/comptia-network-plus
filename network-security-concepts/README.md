# Network Security Concepts

## Intro to IT Security (OB 4.1)

**Logical security** is the protection of data and information systems from unauthorized access, use, disclosure, disruption, modification, or destruction. It involves implementing measures such as firewalls, encryption, access controls, and intrusion detection systems to safeguard digital assets.

## CIA Triad (OB 4.1)

IT security revolves around three main goals, often referred to as the CIA Triad: Confidentiality, Integrity, and Availability.

- **Confidentiality**: Ensuring that sensitive information is only accessible to authorized individuals or systems. This can be achieved through encryption, access controls, and secure communication protocols.

- **Integrity**: Maintaining the accuracy and consistency of data over its lifecycle. This involves protecting data from unauthorized modification, ensuring that it remains trustworthy and reliable. Techniques include checksums, hashing, and digital signatures.

- **Availability**: Ensuring that information and resources are accessible to authorized users when needed. This can be achieved through redundancy, load balancing, and regular maintenance to prevent downtime.

## Confidentiality (OB 4.1)

**Confidentiality** is the principle of keeping information secret and protected from unauthorized access. It is crucial for safeguarding sensitive data, such as personal information, financial records, and intellectual property.

- Confidentiality refers to the measures taken to ensure that sensitive information is not disclosed to unauthorized individuals, entities, or processes.
- It involves preserving authorized restrictions on information access and disclosure, including means for protecting personal privacy and proprietary information.

Here's a breakdown of what confidentiality entails:

- **Access Control**: Mechanisms such as passwords, biometrics, or access cards that limit resource access to authorized personnel to prevent unauthorized access.
  - An ACL (Access Control List) is a list of permissions attached to an object that specifies which users or system processes can access the object and what operations they can perform.
- **Encryption**: The process of converting data into a coded format that can only be read by someone with the appropriate decryption key, ensuring that even if data is intercepted, it remains unreadable to unauthorized parties.
- **Secure Communication**: Using secure protocols (e.g., HTTPS, SSL/TLS) to protect data transmitted over networks from eavesdropping and interception.

> A real-world example of confidentiality in IT security is a healthcare provider protecting patient records. The provider must ensure that only authorized personnel, such as doctors and nurses, have access to sensitive patient information. This can be achieved through access controls, encryption of electronic health records, and secure communication channels when sharing patient data.

## Integrity (OB 4.1)

One of the most important concepts in IT security is to make sure there is only authorized modification of data. This is called **integrity**. It is the assurance that information is accurate and reliable and has not been tampered with by unauthorized individuals.

- Integrity refers to the protection of information from unauthorized modification or alteration, ensuring that data remains accurate and trustworthy throughout its lifecycle.
- Trustworthiness and accuracy of data are maintained by preventing unauthorized changes, whether intentional or accidental.
- Various methods and mechanisms are employed to ensure data integrity, including:
  - **Cryptographic Hash Functions**: These functions generate a unique hash value for a given input, allowing for the detection of any changes to the data. If the hash value changes, it indicates that the data has been altered.
  - **Digital Signatures**: These are used to verify the authenticity and integrity of a message, software, or digital document. A digital signature provides a way to ensure that the content has not been modified since it was signed.
  - **Access Controls**: Implementing strict access controls can help prevent unauthorized users from modifying data, thus maintaining its integrity.

Key aspects of integrity within IT security include:

- **Data Accuracy**: Ensuring that data is correct and free from errors.
- **Data Consistency**: Ensuring that data remains consistent across different systems and over time.
- **Data Trustworthiness**: Ensuring that data can be trusted and is not subject to unauthorized modifications that could compromise its reliability.

> A real-world example of integrity in IT security is if a CEO sends an email to the CFO with a financial report attached. If the report is modified by an unauthorized person, the integrity of the data is compromised, and the CFO may make decisions based on inaccurate information. To prevent this, the CEO could use a digital signature to ensure that the report has not been altered since it was signed.

## Availability (OB 4.1)

It does not matter how secure a system is if it is not available when needed. It's not very useful if your security is so tight that it prevents authorized users from accessing the system. This is where **availability** comes in. It is the assurance that information and resources are accessible to authorized users when needed.

- Availability refers to the principle of ensuring that information and resources are accessible to authorized users when needed, without undue delay or interruption.

Here's how availability is maintained in IT security:

- **Fault Tolerance**: Implementing redundant systems and components to ensure that if one part fails, another can take over without disrupting service.
- **Backup Systems**: Regularly backing up data and systems to ensure that they can be restored in the event of a failure or attack.

The goal of ensuring availability is to prevent downtime and ensure that users can access the information and resources they need to perform their tasks effectively. This is crucial for maintaining productivity and ensuring that critical operations can continue without interruption.

> A real-world example of availability in IT security is a hospital's electronic health record (EHR) system. If the EHR system is unavailable due to a cyber attack or technical failure, healthcare providers may not be able to access patient records, which can lead to delays in treatment and potentially harm patients. To ensure availability, the hospital may implement redundant systems, regular backups, and robust cybersecurity measures to protect against attacks that could disrupt access to the EHR system.

---

In summary, the CIA Triad (Confidentiality, Integrity, and Availability) is a fundamental framework in IT security that helps organizations protect their information and resources from unauthorized access, modification, and disruption.

- **Confidentiality** ensures that sensitive information is kept secret and protected from unauthorized access.
- **Integrity** ensures that information is accurate and reliable, preventing unauthorized modifications.
- **Availability** ensures that information and resources are accessible to authorized users when needed, preventing downtime and ensuring continuity of operations.

## Risk Terms (OB 4.1)

Everything we do in life has some level of risk. What exactly do we mean by risk?

### Risk

In the context of IT security, **risk** refers to the probability of a threat exploiting a vulnerability to cause harm to an asset. It is a measure of the potential loss or damage that could occur as a result of a security incident.

$Risk= \text{Threat} \times \text{Vulnerability}$

This formula indicates that risk is a function of both the likelihood of a threat occurring and the vulnerability of the system to that threat.

When it comes to risk management, we have to ensure that we manage threats and the vulnerabilities that exist in our systems in order to reduce or eliminate risk.

Security is known to be risk-based, which means that we have to make decisions based on the level of risk that we are willing to accept. We cannot eliminate all risks, but we can take steps to mitigate them and reduce their impact.

Before we get into risk management, we need to understand some key terms related to risk:

- **Asset**: An asset is anything of value to an organization, such as data, hardware, software, or intellectual property. Assets can be tangible (e.g., physical devices) or intangible (e.g., reputation).
- **Asset Valuation**: Asset valuation is the process of determining the value of an asset, which can help organizations prioritize their security efforts and allocate resources effectively.
- **Threats**: A threat is any potential danger that could exploit a vulnerability to cause harm to an asset. Threats can be intentional (e.g., cyber attacks) or unintentional (e.g., natural disasters).
- **Threat Agent/Actor**: A threat agent or actor is an individual, group, or entity that has the capability and intent to carry out a threat. This can include hackers, insiders, competitors, or even natural forces.
- **Threat Event**: A threat event is an occurrence that has the potential to cause harm to an asset. This can include a cyber attack, a data breach, or a natural disaster.
- **Threat Vector**: A threat vector is the path or method used by a threat agent to exploit a vulnerability and carry out a threat event. This can include phishing emails, malware, or physical access to a facility.

- **Vulnerability**: A vulnerability is a weakness or flaw in a system that can be exploited by a threat agent to cause harm to an asset. Vulnerabilities can exist in software, hardware, or even in organizational processes.
- **Exposure**: Exposure refers to the extent to which an asset is vulnerable to a threat. It is a measure of how much risk an organization is exposed to based on the vulnerabilities present in their systems.
- **Safeguards/Controls**: Safeguards or controls are measures implemented to reduce or mitigate the risk associated with a threat. These can include technical controls (e.g., firewalls, encryption), administrative controls (e.g., policies, training), and physical controls (e.g., locks, security guards).
- **Attack**: An attack is an intentional act by a threat agent to exploit a vulnerability and cause harm to an asset. This can include cyber attacks, physical attacks, or social engineering attacks.
- **Breach**: A breach is a successful attack that results in unauthorized access to an asset, leading to potential harm or damage. A breach can involve the theft of data, disruption of services, or damage to systems.
  - Attack and breach are often used interchangeably, but an attack refers to the attempt to exploit a vulnerability, while a breach refers to the successful exploitation of that vulnerability.

Keep in mind, everything we do in IT security is based on risk. We should not be doing anything in IT security we have not done a risk assessment for. We need to understand the risks we are facing and make informed decisions about how to manage those risks effectively.

## Authentication (OB 4.1)

When working on a system, you're going to want to make sure that three main concepts are applied: authentication, authorization, and accounting (AAA). These concepts are crucial for ensuring the security of a system and controlling access to resources.

When a user logs into a system, you want to make sure they have the right password, in other words, that they are authenticated, they have access to the correct resources, and that their actions are being logged for accountability. This is where **AAA** comes into play.

### AAA

**AAA** stands for Authentication, Authorization, and Accounting. It is a framework used to manage and control access to resources in a secure manner.

- **Authentication**: The process of verifying the identity of a user or system. This can be done through various methods such as passwords, biometrics, or multi-factor authentication (MFA). The goal of authentication is to ensure that the person or system accessing the resource is who they claim to be.
- **Authorization**: Once the identity of the user or system has been authenticated, authorization determines what resources they are allowed to access and what actions they can perform. This is typically managed through access control lists (ACLs) or role-based access control (RBAC).
- **Accounting or Auditing**: This involves tracking and recording the actions of users or systems to ensure accountability. It allows organizations to monitor access to resources, detect unauthorized activities, and maintain logs for compliance and forensic purposes.

## Multi-Factor Authentication (MFA) (OB 4.1)

**Multi-Factor Authentication (MFA)** is a security mechanism that requires users to provide two or more forms of authentication before granting access to a system or resource. This adds an extra layer of security by requiring multiple pieces of evidence to verify the user's identity.

### Types of Authentication Factors

MFA factors can be categorized into four main categories:

1. **Something You Know**: This includes passwords, PINs, or security questions. It is the most common form of authentication but can be vulnerable to attacks such as phishing or brute force.

- Example: Passwords, PINs, security questions

2. **Something You Have**: This includes physical devices such as smart cards, tokens, or mobile phones. These factors are more secure than something you know because they require possession of a specific item.

- Example: Mobile devices with authentication apps, hardware tokens, smart cards

3. **Something You Are**: This includes biometric factors such as fingerprints, facial recognition, or iris scans. These factors are unique to each individual and are difficult to replicate.

- Example: Fingerprints, facial recognition, iris scans

4. **Somewhere You Are (Location-Based Authentication)**: This factor uses the user's location as a form of authentication and adds contextual security restricting access based on geographic location or network.

- Example: Authentication based on the user's geographic location or network
