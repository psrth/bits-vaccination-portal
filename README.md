# BITS Vaccination Portal

[![Netlify Status](https://api.netlify.com/api/v1/badges/ec919ae6-f1a0-4d59-a0b9-796beec493ea/deploy-status)](https://app.netlify.com/sites/bits-vaccine-portal/deploys)

_As the BITS Pilani campus reopens for students of the 2019 and 2020 batches, a cornerstone of the process has been the Vaccination Portal, a comprehensive system developed by students from DVM to verify student’s vaccination statuses and smoothen the process for the administration._

**BITS Pilani, Pilani campus is one of the first campuses in India to incorporate such a system to ensure a safe return of its students.\***

## Project Description

### Problem Statement

With more than 2500 students being called back to campus as the pandemic eased up, we needed to find a way to ensure that students were vaccinated and being safe about their arrival. The immediate problem was to have a system to verify whether students were vaccinated, track how many vaccines they had received, ensure the validity of each certificate, and track where students were returning to campus from. Without automating this process, it would be a mountain of data for the administration to have to manually sit and verify.

### Research

As soon as we heard that the campus would be re-opening, we realised the impossible task that SWD would have to undertake in order to manually scan thousands of certificates and manually keep track of student data in various sources. We started to research and try to find a way to automatically verify students’ vaccination status and have all the data in a single-source-of-truth database for easy access.

### Implementation

After extensively reading and analysing the Indian Government’s CoWIN API (official application programming interface), we devised an automated solution to read PDFs and verify them with the official Government database. The system was simple — a student would upload their PDF, the backend would process the document, read the QR code, transpile the data and then query it against the Government database. We then cross-referenced the data with the student’s data according to their BITS email address and returned a vaccination status for the student.

This, while being a near-perfect solution, still left out certain edge cases. For example, students who might not have been vaccinated in India, or students who had different names on their certificate and BITS email. Thus, we also built a manual verification system — in case a student had certain difficulties with being automatically verified, an authorised member of SWD could log into a backend interface and manually verify the students.

### Platform

Having sorted out the logic and functioning of the portal, we now needed to devise a clean and easy-to-use interface for both the student body and the admin personnel at SWD. Thus, we built two separate portals — https://vaccination.bits-dvm.org for the student body, and https://vaccination-admin.bits-dvm.org for SWD.

<img src="https://i.imgur.com/LKQbhCm.png" alt="BITS Vaccine Portal — Students" style="width:80%;"/>

The student portal is a clean interface that allows only certain batches to access the portal at one time. Once approved students log in with their BITS email, they can quickly see their vaccination status. They are then able to upload their vaccine certificate, signed parents consent form, date of arrival, location, and agree to certain health declarations. Once they add all their details, the lightning-fast portal updates instantly with the student’s new vaccination status.

<img src="https://i.imgur.com/4sEUqdC.png" alt="BITS Vaccine Portal — Admin" style="width:80%;"/>

The admin portal is a functional tool for the SWD team to quickly access any details they may require. Any authenticated member has controls over which batches can currently update their vaccination details. They also have the power to instantly download a physical copy of all the students in an Excel spreadsheet format. On the admin portal, they can filter down the students by batches/vaccination status/date of arrival or search by name in order to quickly access a group of students at once. Each student has their own page where the admin can see all their details, the uploaded PDFs and even manually update their status.

### Usage

The reception to the portal has been amazing — students of all batches and branches alike have commended the easy-to-use nature of the portal and were easily able to provide all the requested data to the SWD. After two batches have used this portal to submit their information, the SWD now has access to all the data without having to manually scan even a single certificate in one, consolidated database.

<img src="https://imgur.com/9pYU2Ea.png" alt="BITS Vaccine Portal — Analytics" style="width:60%; border: 10px solid white;"/>

With over 4.5k users to date and counting, we’re extremely proud of the Vaccine Portal and honoured to be able to share this with our student body and the BITS administration.

_(last updated on 12th September, 2021)_

## Installation

This app was made with <3 by students from BITS Pilani, using **React.js** for the frontend and **Node.js** for the backend. It uses the **Chakra-UI library, Google O-Auth,** and **Docker+Nginx** for hosting.

In case you'd like to run this on your local machine, follow these steps:

**Clone the repository**

```
git clone https://github.com/psrth/bits-vaccination-portal.git
```

**Build the clients**

```
cd vaccine-portal
npm install
npm start
```

```
cd vaccine-admin-portal
npm install
npm start
```

In case you'd like to contribute or squash a bug, just open a pull request!

## Developers

**Parth Sharma** (Frontend Developer)  
**Mohit Makwana** (Backend Developer)

**Nidheesh Jain** (Frontend Mentor)  
**Anshal Shukla** (Backend Mentor)  
**Darsh Mishra** (Backend Mentor)

## License

This code is the intellectual property of BITS Pilani and the developers listed above. In case you'd like to repurpose some of this code, please get in touch with one of the developers so that we can get you explicit permission to use the codebase.
