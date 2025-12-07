---
title: "Blog 1"
date: "2025-06-25"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Shield AI and AWS Collaborate to Deliver Mission Autonomy at Formation Scale

**Authors:** Keith Johnson, Tim Wilson, and Sean Park | **Date:** June 25, 2025  
**Tags:** Amazon Elastic Container Registry, Announcements, Artificial Intelligence, AWS IoT Core, Defense, Government, Internet of Things, Public Sector

---

## Introduction

The rapid evolution of autonomous systems in defense and other sectors is creating new challenges in software deployment and management. Market analysis emphasizes this trend, with the global military unmanned aerial vehicle (UAV) market projected to expand at an estimated compound annual growth rate of 11.2% through 2033.

The significant growth of military UAVs—which are viewed as representative of the broader autonomous systems market—highlights the urgent need for scalable, secure, and efficient software deployment solutions. As the number of autonomous platforms increases, so does the complexity in managing their software. In response to these challenges, Shield AI and Amazon Web Services (AWS) have collaborated and successfully demonstrated a scalable architecture and proof of concept (PoC) to address the common issues encountered when deploying autonomous software and machine learning algorithms to autonomous systems. By integrating Shield AI's platform-agnostic autonomous software development suite, Hivemind Enterprise, with AWS IoT Core and Amazon Elastic Container Registry (ECR), autonomous system developers can develop a Hivemind Pilot and—after simulation and testing are complete—deploy it directly to the hardware platform of their choice from the AWS cloud using command line interface (CLI) or Hivemind's user interface.

---

## Challenges in Autonomous System Deployment

For defense customers deploying autonomous systems, software deployment encounters numerous challenges, including:

- **Scaling across multiple vehicle types**: Supporting air, ground, and maritime autonomous vehicles
- **Mission-specific collaboration**: Increasing demand for coordination between vehicles
- **Rapid deployment in DDIL environments**: The necessity to rapidly deploy updates across large fleets of vehicles in denied, disrupted, intermittent, and limited (DDIL) environments

Emerging conflicts demand rapid software updates and reconfiguration across different system software components. From integrated control firmware, mission machine learning models, to "AI pilots," these updates must be deployed securely and reliably to vehicle formations, ensuring system integrity to counter evolving threats and mission requirements. While many aspects of autonomous vehicle systems such as advanced hardware, sensors, navigation, and autonomous perception have made rapid progress, updating these systems often requires time-consuming manual processes that can slow initial development and testing of new capabilities, create bottlenecks during mission execution, and create opportunities for misconfiguration.

**Liz Martin, DoD General Manager at AWS**, emphasized the importance of this collaboration:

> "Our defense customers need rapid autonomous software updates to maintain readiness and respond to emerging mission requirements. Through the collaboration between Shield AI and AWS, we have a solution that delivers development and deployment of mission autonomy capabilities at formation scale across autonomous platforms."

---

## The Solution

The collaboration addressed the challenge of updating autonomous systems by building a flexible solution that uses AWS IoT Core as a scalable and secure mechanism to orchestrate updates and state between Shield AI's software stacks (Edgeos) running on autonomous hardware platforms and Shield AI's autonomous development platform. Because Hivemind pilots are deployed as containers, once a new deployment is ready and communicated via AWS IoT Core to the autonomous platform, the container is securely fetched from Amazon ECR where it is hosted by Hivemind as part of the development and deployment integration, creating a cloud-hosted approach.

In summary, the solution enables:

- **Centralized control and rapid deployment** of Hivemind pilot software
- **Secure, cloud-based distribution** to field systems
- **Scalable management** of large autonomous fleets
- **Real-time monitoring and control** of deployment processes

**Nathan Michael, Chief Technology Officer at Shield AI**, stated:

> "Developing autonomy is both complex and expensive—but with AWS, we're making it faster, easier, and more scalable. This collaboration combines Hivemind Enterprise autonomy systems and AWS infrastructure to streamline how customers develop, deliver, and maintain intelligent autonomous systems across large distributed fleets."

---

## Benefits for Defense and Commercial Customers

The collaboration brings advantages to both defense and commercial customers. Defense customers can now maintain high levels of mission readiness by rapidly updating their autonomous fleets to counter emerging threats and adapt to changing mission parameters. This capability comes with increased operational flexibility, allowing teams to quickly modify autonomous capabilities for new environments and mission types. The solution also enhances security measures by ensuring all platforms consistently run secure, up-to-date software versions, while providing centralized management and monitoring capabilities for autonomous platforms.

### Commercial Applications

In the commercial realm, benefits extend across multiple industries:

- **Agriculture**: Operations can now efficiently update self-driving tractor fleets to adapt to seasonal changes and implement new farming techniques
- **Oil & Gas**: The industry can deploy critical updates to offshore autonomous systems, enhancing both safety protocols and operational efficiency
- **Logistics and Warehousing**: Businesses can seamlessly modify their autonomous vehicle fleets to adapt to evolving inventory requirements and routing needs
- **Mining**: Operations benefit from the ability to quickly update autonomous equipment to accommodate new terrain conditions or extraction methods

---

## Conclusion

The collaboration between Shield AI and AWS addresses a critical challenge in autonomous system management. By demonstrating rapid, secure deployment of mission autonomy software, we are enabling organizations in both defense and commercial sectors to maximize the power of their autonomous fleets. This integration also establishes a foundation for post-mission data collection, which is crucial for driving rapid pilot development and continuous improvement of autonomous capabilities. In the next phase of collaboration, we are moving from proof of concept to production, and we are excited to explore how this solution will transform operations and unlock new possibilities in autonomy.

---

## About the Authors

### Keith Johnson

Keith is the Chief Technologist for AWS's United States Department of Defense (DoD) business. Keith leads a team of experienced solution architects who serve as trusted technical advisors to DoD customers, guiding them to maximize business and mission outcomes by leveraging AWS solutions and best practices. Keith joined AWS in May 2022.

### Tim Wilson

Tim is the Principal IoT Specialist for AWS's United States Federal Specialist team. In this role, Tim works with AWS United States Federal customers and partners to help them adopt and use AWS IoT services and solutions. He started working at AWS as a solutions architect in 2012.

### Sean Park

Sean is a Principal Customer Executive at AWS, supporting the Department of Defense (DoD) and driving innovative critical capabilities with partners. Outside of work, he enjoys seeking out new culinary adventures with his wife and two children.
