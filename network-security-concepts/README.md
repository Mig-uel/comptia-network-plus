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
