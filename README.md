# LeetCode Daily Problems

This folder has the lecture notes of Daily problems of Leetcode [CodestorywithMIK]

# SystemDesign-Notes

System Design Folder - has the system design playlist lecture notes [Aditya Tandon]





## Design and Architecture (CO-1, CO-3)

### System Overview

Our patient care management application is designed as a multi-role healthcare monitoring system that serves family members and caregivers in managing patient care. The architecture follows a modular, component-based design that ensures clear separation of concerns and maintainability.

### Core Architectural Components

#### 1. Authentication and User Management Component

**Purpose:** Manages user authentication, authorization, and role-based access control for the entire system.

**Functionality Areas:**
- **User Registration and Login:** Handles account creation, credential validation, and JWT token management for secure sessions
- **Role-Based Access Control:** Implements permission systems differentiating between Primary Admin Caregivers, Secondary Caregivers, and Family members
- **Patient Profile Creation:** Manages the initial setup workflow where Primary Admins create patient profiles and establish caregiver-patient relationships
- **Invitation Code System:** Generates and validates invitation codes for linking secondary users to existing patient profiles

This component directly addresses CO-1 (User Authentication & Authorization) and CO-3 (Role-Based Functionality) requirements.

#### 2. Emergency Response Management Component

**Purpose:** Orchestrates emergency scenarios including overdose detection and fall incidents, ensuring rapid response and appropriate escalation.

**Functionality Areas:**
- **Emergency Detection:** Handles manual overdose reporting and fall detection through caregiver input
- **Severity Assessment:** Processes emergency severity classification (Moderate, High, Critical) and determines response protocols
- **Notification Dispatch:** Manages multi-channel communication (push notifications, SMS, email) to family members and emergency services
- **Escalation Workflow:** Implements time-based escalation protocols when acknowledgments are not received within specified timeframes
- **Emergency Event Logging:** Captures comprehensive incident data including timestamps, severity levels, and resolution status

#### 3. Patient Data Management Component

**Purpose:** Serves as the central repository for all patient-related information, ensuring data integrity and comprehensive health tracking.

**Functionality Areas:**
- **Behavioral Logging System:** Enables caregivers to record daily observations including mood assessments, behavioral patterns, and meal tracking
- **Memory Stimulation Activities:** Manages creation and execution of personalized cognitive exercises, tracks patient responses, and maintains progress analytics
- **Patient Profile Management:** Maintains comprehensive patient records including medical history, family information, and care protocols
- **Data Validation:** Ensures all logged data meets quality standards and maintains consistency

#### 4. Communication and Notification Component

**Purpose:** Manages all outbound communications, ensuring timely and appropriate delivery of information to relevant stakeholders.

**Functionality Areas:**
- **Multi-Channel Notification Engine:** Supports push notifications, SMS, and email with delivery confirmation tracking
- **Recipient Management:** Maintains contact lists for family members, caregivers, and emergency services with role-based preferences
- **Message Customization:** Generates context-aware messages based on emergency type, severity, and recipient role
- **Family Notification Coordination:** Manages notification workflows ensuring appropriate family members are informed based on the situation

#### 5. Analytics and Reporting Component

**Purpose:** Processes historical data to provide insights into patient health trends and system effectiveness.

**Functionality Areas:**
- **Trend Analysis Engine:** Processes historical log data to identify patterns in patient behavior and health indicators
- **Performance Metrics Calculation:** Generates statistics on response times, acknowledgment rates, and emergency resolution effectiveness
- **Visualization Services:** Creates charts, graphs, and summary reports for caregivers and family members
- **Progress Tracking:** Monitors improvement in cognitive exercises and behavioral patterns over time

### Major Design Patterns

#### Model-View-Controller (MVC) Pattern
The application follows MVC architecture where:
- **Models** represent patient data, user accounts, and system configurations
- **Views** provide role-specific user interfaces for caregivers and family members
- **Controllers** manage interaction between models and views, implementing business logic and data validation

#### Observer Pattern
Implemented in the notification system where:
- Emergency events act as subjects that notify registered observers (family members, caregivers, emergency services)
- The system automatically updates all relevant parties when patient status changes or emergencies occur

#### Strategy Pattern
Used in the emergency response component where:
- Different notification strategies are selected based on severity levels
- Various escalation protocols are implemented as interchangeable strategies
- Communication methods are selected dynamically based on recipient preferences

### External System Integration

The architecture includes external system interfaces:

#### Communication Services
- SMS gateway integration for emergency notifications
- Email service providers for routine communications
- Push notification services for mobile app alerts

#### Emergency Services Integration
- Direct API connections to emergency medical services for critical situations
- Integration with local emergency contact systems

### Component Relationships

The components work cohesively through well-defined interfaces:
- The Authentication Component validates access for all other components
- The Emergency Response Component coordinates with Patient Data Management for logging and the Communication Component for notifications
- The Analytics Component processes data from Patient Data Management for trend analysis
- All components interact through standardized APIs ensuring modularity and replaceability

This architecture provides a unified, comprehensive patient care management solution that addresses all specified requirements with appropriate security, scalability, and reliability measures while maintaining clear relationships between system requirements and component functionality.
