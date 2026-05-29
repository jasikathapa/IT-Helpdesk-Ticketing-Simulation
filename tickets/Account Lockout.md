
# 🎫 Ticket: Account Lockout

## Ticket ID
HD-0001

## Category
Authentication Issue

## Priority
High

## User Reported Issue
User account locked after multiple failed login attempts.\

## Investigation Performed
- Verified user identity
- Reviewed account status in Active Directory
- Confirmed account lockout condition
  
---

## Resolution

https://github.com/user-attachments/assets/c10f8b3b-e882-4734-b98b-fa3205f3eb07

- Reset password in Active Directory Users and Computers
- Enabled "User must change password at next logon" ✔
- Enabled "Unlocked user account" ✔
- Provided temporary credentials to user
- Advised user regarding password policy requirements 

---

## Outcome
User successfully regained access and created a new password during login.
