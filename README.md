# Implementing Conditional Access for Secure Remote Access with MFA and Entra Identity Governance

## Overview
This project demonstrates the implementation of **Conditional Access (CA)** policies for securing remote access to critical applications, paired with **Identity Governance** tools like **Access Reviews** and **Entitlement Management**. The focus is on enforcing Multi-Factor Authentication (MFA), securing access for remote workers, and establishing role-based access governance for critical business applications.

## Goals
1. Secure remote access with MFA enforcement for high-risk users.  
2. Block access from untrusted locations to protect against unauthorized logins.  
3. Ensure proper access governance with Access Reviews and Role-Based Access Control (RBAC) for Finance and HR roles.  

---

## Environment Setup
### Test Users
- Created users to simulate real-world scenarios:
  - **RemoteUser**: Remote worker requiring access to core applications.
  - **FinanceUser**: Employee with access to finance-specific resources.
  - **HRUser**: Employee with HR application access.

### Test MFA
- Enforced MFA for **RemoteUser** and **FinanceUser** to simulate secure remote access.

**Screenshots**:  
1. Screenshot of test users created in Azure AD.  
2. Screenshot of MFA setup for selected users.

---

## Conditional Access Policies
### Secure Remote Access Policy
- **Objective**: Enforce MFA for remote workers and block access from untrusted locations.  
- **Configuration**:
  1. Navigate to **Azure AD** > **Security** > **Conditional Access**.
  2. Create a policy targeting the **RemoteWorkers** group.
  3. Conditions:
     - **Locations**: Allow access only from trusted locations.
  4. Access Controls:
     - Grant access only if MFA is satisfied.

### Finance Access Policy
- **Objective**: Enforce MFA for users accessing finance applications based on sign-in risk.  
- **Configuration**:
  1. Create a second policy targeting the **Finance** group.
  2. Conditions:
     - **Sign-In Risk**: Require MFA for medium or high-risk users.

**Screenshots**:  
1. Screenshot of Secure Remote Access policy setup.  
2. Screenshot of Finance Access policy settings.

---

## Identity Governance
### Access Reviews
- Configured quarterly access reviews for the **RemoteWorkers** group to ensure appropriate access to critical applications.  
- **Reviewers**: Assigned to group owners and managers.

### Entitlement Management
- Set up **Access Packages** for Finance and HR roles to enable role-based access requests.  
- **Configuration**:
  1. Created catalogs for **Finance** and **HR** departments.
  2. Enabled approval workflows for access requests.  

**Screenshots**:  
1. Screenshot of Access Reviews configuration.  
2. Screenshot of Entitlement Management setup.

---

## Testing and Results
### Simulated Risk Events
- Triggered multiple incorrect login attempts and VPN-based sign-ins to simulate risky behaviors:
  - High-risk IP addresses.
  - Untrusted locations.

### Policy Enforcement
- Verified the following:
  1. MFA was required for **RemoteUser** and **FinanceUser** during high-risk scenarios.
  2. Access was blocked for users signing in from untrusted locations.

**Screenshots**:  
1. Screenshot of MFA prompt during simulated high-risk login.  
2. Screenshot of blocked access message for untrusted locations.

---

## Results
1. Improved security by enforcing MFA for remote workers and finance users.  
2. Established proper governance with Access Reviews and role-based access control.  
3. Mitigated risks by blocking unauthorized logins from high-risk or untrusted locations.  

---

## Documentation
For detailed setup instructions and configurations, refer to the [Full Project Documentation](docs/Conditional_Access_Secure_Remote_Access.pdf).

---

## Contact
For any questions or further information about this project, feel free to reach out:
- **Email**: rlass8908@gmail.com  
- **LinkedIn**: [Roman Lassiter](https://linkedin.com/in/roman-lassiter)

---
