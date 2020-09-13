# NSU_project_v2.0

Remote control system of university leisure places

## The problem to be solved
Our university (Novosibirsk State University) has a number of leisure / study areas equipped with sandbags, chairs, tables and blackboards. During classes it can be difficult to find a suitable place for yourself and your friends to study / discuss something - most of them are partially or fully occupied. Therefore, students have to wander around the university building for a long time in search of a free sandbag for reflection. 

Personally, we see two solutions to this problem:
 - Make more practice areas (Not interesting, since this is a purely administrative issue)
 - Create a system for remote control and search for free seats.

Therefore, the idea of the project is to create an automated and remote control system of university recreational places. User interaction with the system is implied through a mobile application

## Project risks
The first and one of the most serious problems that we face at the very beginning is the administrative one. We need to install additional cameras above the recreation areas or gain access to existing ones. To do this, we plan to contact the dean's office of our faculty, or with the deputy head of the department of the property complex of the NSU, responsible for video surveillance at the university. The problem is that we may not be approved of the planned actions. The solution is to search for alternative areas outside NSU, similar in functionality and external qualities to university leisure areas. 
The next equally important problem (not even a problem, but rather a possible justified risk) is damage or theft of technical equipment, including cameras and hardware. To avoid this, it is possible, by prior agreement with the administration, to fasten all equipment to the ceiling, making reliable enclosures. At the hardware level, it is possible to install sensors that notify in case of damage.

## Software and hardware
In technical terms, we are planning to use single-board computers called Raspberry Pi 4. At the moment we have two such devices at our disposal. As cameras, it is planned to use ordinary web cameras or Raspberry Pi cameras (official cameras for the aforementioned computers, we have one such). Based on the fact that we have two devices, we have an idea to create a cluster (use one raspberry to recognize objects and control cameras, the other to serve mobile devices as a server) using modern control systems. 
