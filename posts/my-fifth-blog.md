---
title: 5. Exploring API Integration for Sydney offline vintage event
date: 2026-05-10
author: Qiuyue Xu
summary: Investigating how map APIs can support offline vintage event and enhance the technical functionality of the VintArchive platform.
tags:
  - API Integration
  - OpenStreetMap
  - Technical Decisions
---
As the project developed further, I began exploring how external APIs could extend the functionality of the platform. One key insight identified during earlier user research was that users strongly preferred local, in-person transactions, as they were perceived to be safer and more trustworthy than remote exchanges. This led me to investigate how map-based APIs could support local trading interactions within Sydney.

APIs (Application Programming Interfaces) allow applications to communicate with external services and retrieve data or functionality without building everything from scratch. Rather than developing a custom map system independently, APIs allow developers to integrate existing services such as maps, geolocation, and routing into a web application. This makes development more efficient while also introducing real-world technical considerations such as authentication, quotas, and security.

To experiment with this idea, I used **Leaflet.js** together with **OpenStreetMap** to prototype a Sydney-based exhibition map for the VintArchive platform.

![map in exhibition](/DECO2017_blog/assets/images/map.png)

This creates an interactive map centred on Sydney, reinforcing the platform’s intentionally local scope. Instead of treating vintage trading as a global marketplace, the project focuses specifically on Sydney-based exchanges to improve trust, feasibility, and community connection.

When users click a marker, a popup displays the exhibition name and short description. This creates a more engaging and spatial browsing experience compared to a traditional text-based list.

From a functional perspective, the map API supports several important user needs identified during research:

- Users can visually browse nearby exhibitions and vintage events.
- The platform reinforces safer local interactions.
- Physical community participation becomes more visible and accessible.
- The website moves beyond static content into interactive spatial experiences.

The implementation also demonstrates alignment between technical decisions and functional requirements. Instead of adding APIs purely for visual novelty, the map directly supports earlier research findings regarding trust, local exchange, and community engagement.

However, integrating APIs also introduces constraints and responsibilities. During the lecture, particular emphasis was placed on API security and credential management. API keys should never be committed to public repositories, as removing them in later commits does not erase them from Git history. If exposed, they should be treated as compromised immediately. This highlighted the importance of using .env configuration files and .gitignore to securely manage credentials during development.

Additionally, APIs often operate under usage quotas and rate limits. Although OpenStreetMap itself is free and open-source, some commercial mapping services charge fees based on request volume. Due to the limited scope and timeframe of this assignment, the map functionality remains intentionally lightweight. Rather than implementing advanced real-time navigation or location tracking, the prototype focuses on displaying exhibition locations and supporting basic local discovery.

Overall, exploring API integration expanded the project beyond interface design and introduced considerations around external services, scalability, security, and implementation feasibility. The map feature demonstrates how technical systems can directly respond to user research insights while supporting the broader goal of building a community-oriented vintage platform.