# Identity Lifecycle Management (JML) Workflow & Control Assessment for Northstar Medical Group

## Problem Statement

- Northstar Medical Group is growing, but its employee access process hasn’t kept up. Department transfers are handled inconsistently, and former employees may retain access after leaving. Without a reliable process for approving, completing, and verifying access changes, the organization faces unnecessary exposure to sensitive patient data and potential HIPAA compliance risks.
  - Employees retain permissions from previous roles after transferring departments.
  - Access changes depend on manual communication between HR, managers, and IT.
  - There’s limited evidence showing who approved access, what changed, and whether access was removed on time.

**Questions that must be answered:** 
- Who requests and approves access changes?
- Who creates accounts and assigns permissions?
- When should access be provisioned?
- What must be removed when someone changes roles?
- Who notifies IT when an employee leaves, and how quickly must access be revoked?

## Solution Overview

- I designed a simulated Joiner-Mover-Leaver (JML) workflow to bring structure, accountability, and verification to employee access changes. Following one employee from hire to department transfer to departure, I mapped the approvals, provisioning steps, access removals, and control checks needed at each stage.

## Video Walkthrough
- https://www.loom.com/share/97e2a1161e7844d7a715fc3900747eee

## Workflow: One Employee, Three Access Changes
<img width="1536" height="1024" alt="Identity Lifecycle Management Workflow" src="https://github.com/user-attachments/assets/28858c88-bdc2-4f04-9775-f4e9a5c34f1e" />

### 1. Joiner — Registered Nurse

**Scenario:** Sarah Mitchell joins Northstar Medical Group as a registered nurse and needs access to clinical systems before her first shift.

- **Trigger:** HR confirms Sarah’s hire, department, manager, and start date.
- **Request & Approval:** Her hiring manager identifies the systems and permissions needed for her role and approves the access request. Additional approval is obtained where required by application policy.
- **Provisioning:** IAM/IT creates her account and assigns the approved permissions based on her job responsibilities.
- **Verification & Evidence:** Access is checked before her first day, and the request, approvals, and completion status are documented.

**Control objective:** Ensure access is approved, role-appropriate, and ready when needed—without granting unnecessary permissions.

### 2. Mover — Transfers to Revenue Cycle

**Scenario:** Sarah transfers from nursing to Revenue Cycle. Her new responsibilities require different systems, but her previous permissions may still be active.

- **Trigger:** HR or her manager submits a role-change notification with the effective date and new department.
- **Request & Approval:** Sarah’s receiving manager identifies and approves the access required for Revenue Cycle. Existing permissions are reviewed against her new responsibilities.
- **Access Changes:** IAM/IT removes nursing-related group memberships and application permissions that are no longer justified, then assigns the approved Revenue Cycle access.
- **Verification & Evidence:** The updated access is checked, removed permissions are confirmed, and the changes and approvals are documented.

**Control objective:** Prevent *permission creep*. A transfer is not complete simply because new access has been granted; old access must also be reviewed and removed when no longer needed.

### 3. Leaver — Leaves Northstar

**Scenario:** Sarah leaves Northstar Medical Group. Her access must not remain active after her authorized employment period ends.

- **Trigger:** HR notifies IAM/IT of Sarah’s departure and effective date and time.
- **Account Disablement:** IAM/IT disables her account at the required time under organizational policy. Urgent or involuntary departures may require immediate action.
- **Access Revocation:** Relevant sessions are terminated and separately managed application access is revoked as applicable. Remaining group memberships, entitlements, and access paths are checked.
- **Verification & Evidence:** IT records when the account was disabled, confirms required revocation steps are complete, and escalates any access that remains active.

**Control objective:** Ensure departures trigger timely, verifiable access removal—not just an account change that leaves other access paths open.

## Key Questions Answered

- **Who requests and approves changes?** HR confirms employment events; managers request or validate role-based access; the receiving manager approves access for a new role. Sensitive application access may also require application-owner approval.
- **Who creates the account?** IAM/IT provisions the account and assigns permissions after required requests and approvals are in place.
- **When should access changes begin?** Once the employment event and effective date are confirmed, with onboarding access ready before the first day and transfer or departure actions aligned to the required effective time.
- **What old access must be removed after a transfer?** Previous-role security-group memberships, application entitlements, and role-specific permissions that are no longer justified. Retained access should have a documented business need.
- **Who notifies IT when someone leaves, and how quickly is access removed?** HR or an authorized departure-notification owner informs IAM/IT. Access is disabled at the policy-defined departure time, with immediate action when required for urgent departures. Completion is verified and documented.

## Key Achievements

- Built a clear workflow showing how HR, managers, and IAM/IT coordinate access from an employee’s first day through a role change and departure.
- Worked through how outdated permissions can slip through during transfers and identified checks to catch and remove access that no longer matches the employee’s job.
- Connected approvals, deadlines, verification, and documentation into one process so access decisions have clear ownership and a record of what was done.
