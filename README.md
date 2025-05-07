# Exchange Online Administration

![MS 365 Road Map](https://github.com/sanele176/Exchange-Admin/blob/main/Microsoft-365-Cloud-Collaboration-Engineer.png)



# 📂 Exchange-Admin

## 📘 Overview

**Exchange-Admin** is a curated collection of PowerShell scripts designed to streamline Microsoft Exchange and Active Directory administration. These scripts help automate repetitive tasks, enforce standard configurations, and assist in troubleshooting common issues across hybrid or cloud environments.

> 🎯 **Target audience:** IT administrators, Exchange engineers, and sysadmins working in Microsoft 365 or hybrid Exchange environments.

---

## 📦 Features

| Category                | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Distribution Groups**| Bulk add/remove/update users, convert to mail-enabled groups, set permissions |
| **Mailbox Delegation** | Assign Send As, Full Access permissions and verify propagation               |
| **Archiving**          | Enable online archives for users or groups                                  |
| **User Queries**       | Export user lists, audit password age, check permissions                    |
| **Policy Management**  | Assign retention policies, enforce mailbox limits                            |

---

## 🛠 Requirements

- **PowerShell 5.1+**
- **Exchange Online Management Module**
- **Global Admin or Exchange Admin role**
- **AzureAD or MSOnline module** (for certain user queries)

> 🧪 Tested on Windows 10/11, Exchange Online (M365), and hybrid environments

---

## 📂 Repository Structure

```
Exchange-Admin/
├── DL/
│   ├── Add-UserToDL.ps1
│   ├── Update-DLMembersBulk.ps1
│   ├── Convert-DLtoMailEnabled.ps1
│   └── Get-UsersWithSendAs.ps1
├── Mailbox/
│   ├── Delegate-MailboxAccess.ps1
│   ├── Enable-OnlineArchive.ps1
│   ├── Apply-RetentionPolicy.ps1
├── Users/
│   ├── Export-ActiveUsers.ps1
│   ├── Check-PasswordLastSet.ps1
├── README.md
└── LICENSE
```

---

## 📄 Script Descriptions

### 🔹 DL Management

- **Add-UserToDL.ps1**  
  Adds a single or multiple users to a specified Distribution List.

- **Update-DLMembersBulk.ps1**  
  Bulk update DL members using a CSV input.

- **Convert-DLtoMailEnabled.ps1**  
  Converts traditional DLs to mail-enabled security groups for better control.

- **Get-UsersWithSendAs.ps1**  
  Audits DLs and lists users with “Send As” permissions.

### 🔹 Mailbox Operations

- **Delegate-MailboxAccess.ps1**  
  Assigns Send As and Full Access permissions to specified users.

- **Enable-OnlineArchive.ps1**  
  Enables archive mailboxes for a user or list of users.

- **Apply-RetentionPolicy.ps1**  
  Applies a retention policy to specified user mailboxes.

### 🔹 User Utilities

- **Export-ActiveUsers.ps1**  
  Exports all enabled users in Active Directory to CSV.

- **Check-PasswordLastSet.ps1**  
  Checks when each user last changed their password.

---

## ▶️ Usage

Each script is designed to be run as a standalone task or scheduled job. Basic usage examples are provided below:

```powershell
# Add user to a DL
.\Add-UserToDL.ps1 -DLName "HR Team" -UserEmail "john.doe@domain.com"

# Assign delegated access to mailbox
.\Delegate-MailboxAccess.ps1 -Mailbox "HRMailbox" -User "john.doe@domain.com" -AccessType "FullAccess"
```

> 💡 For bulk operations, provide a properly formatted CSV file as input.

---

## ⚠️ Notes

- For hybrid Exchange environments, changes may need to be initiated from on-prem.
- Some operations require replication time across AD and Exchange.
- Ensure MFA is disabled or use an app password if running non-interactively.

---

## 🤝 Contributing

Want to improve or add new scripts?

1. Fork the repository.
2. Create a new branch: `feature/add-script-name`
3. Submit a pull request with documentation.
4. Adhere to the PowerShell Best Practices guide (naming, error handling, parameter validation).

---

## 📜 License

[MIT License](LICENSE)

---

## 💬 Contact

Maintained by **[Sanele](https://github.com/sanele176)**  
For questions, open an [Issue](https://github.com/sanele176/Exchange-Admin/issues)
