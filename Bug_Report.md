# Bug Report

## Overview

During testing, I came across several issues within the voice assistant application. Some of these are major issues, while others are minor but still important for overall user experience. The findings include incorrect availability displayed for an invalid leap-day date, omission of the appointment type in SMS confirmations, limitations in providing parking facility information, and mispronunciation of certain names. Addressing these issues would improve system accuracy, clarity of communication, and overall user satisfaction.

## Issues Identified

### 1. Leap-Day Scheduling Validation Issue

- **Context**: An attempt was made to schedule an appointment for **February 29, 2026**.
- **Observed Behavior**: The assistant indicated that it could not complete the booking; however, appointment slots for that date were visible within the system.
- **Clarification**: February 29, 2026 is not a valid calendar date, as 2026 is not a leap year. Therefore, the system should neither display availability nor allow booking attempts for that date.
- **Impact**: Displaying appointment slots for an invalid date creates inconsistency between scheduling logic and system validation. This may result in confusion, failed booking attempts, and unnecessary escalations to human representatives.
- **Recommendation**:
	- Implementing strict date validation to prevent invalid calendar dates (such as February 29 in non-leap years) from being generated or displayed.
	- Ensuring the scheduling and availability logic are aligned so that invalid dates cannot surface in the system.


### 2. SMS Confirmation Missing Appointment Type

- **Context**: After successfully booking an appointment, the SMS confirmation included the date, time, provider name and location but did not include the appointment type (e.g., “New Consultation,” “Physical Therapy”).
- **Impact**: Without the appointment type, recipients may be uncertain about the specific service scheduled, if they have multiple appointments and potentially leading to confusion or additional follow-up inquiries.
- **Recommendation**:
	- Revising the SMS template to ensure the appointment type is included.


### 3. Parking Facilities information

- **Context**: When asked whether parking facilities were available near the hospital, the assistant responded that it did not have that information and offered to transfer the call to a representative.
- **Observed Behavior**: The assistant was unable to provide basic facility-related information and defaulted to escalation.
- **Impact**: Although not a critical defect, this behavior increases call transfers for general informational queries that could reasonably be handled by the assistant. This may reduce operational efficiency and user satisfaction.
- **Recommendation**:
	- Expanding the assistant’s knowledge base to include common facility-related information (e.g., parking availability, directions, Landmarks).

### 4. Mispronunciation of Names

- **Context**: During live calls, the assistant mispronounced certain regional names.
- **Impact**:  Incorrect pronunciation may lead to awkward interactions and reduce the overall user experience.
- **Recommendation**:
	- Expanding the TTS pronunciation dictionary to better support regional names.
	- Consider allowing phonetic guidance or metadata-based pronunciation hints for recurring contacts.
	