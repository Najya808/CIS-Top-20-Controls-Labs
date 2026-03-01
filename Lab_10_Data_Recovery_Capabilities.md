# Lab 10 — Data Recovery Capabilities

## Objective
To understand the importance of data recovery by performing manual and scheduled backups, restoring data, and verifying data integrity on a Linux system.

---

## Tools & Environment
- Ubuntu Linux (Test VM)
- Terminal (CLI)
- tar utility
- cron (Scheduled Tasks)
- diff utility

---

## Task 1 — Select Data for Backup

Selected directory:

/home/user/Documents

This folder contains important files that require backup protection.

---

## Task 2 — Perform Backup Operations

### Subtask 2.1 — Manual Backup

Created a compressed archive using:

```bash
tar -czvf DocumentsBackup.tar.gz /home/user/Documents
```

Explanation:
- `-c` → Create archive
- `-z` → Compress using gzip
- `-v` → Verbose output
- `-f` → Specify filename

✅ Result:
Backup archive successfully created in current directory.

---

### Subtask 2.2 — Scheduled Backup (Cron Job)

Edited crontab:

```bash
crontab -e
```

Added scheduled backup at 2 AM daily:

```bash
0 2 * * * tar -czvf /home/user/DocumentsBackup_$(date +\%F).tar.gz /home/user/Documents
```

Explanation:
- Runs daily at 2:00 AM
- `$(date +\%F)` appends current date
- Automates backup process

✅ Result:
Automated daily backups configured successfully.

---

## Task 3 — Restore & Verify Backup

### Subtask 3.1 — Restore Backup

Extracted backup to a separate directory:

```bash
tar -xzvf DocumentsBackup.tar.gz -C /home/user/RestoredDocuments
```

Explanation:
- `-x` → Extract archive
- `-z` → Decompress gzip
- `-v` → Verbose
- `-f` → File name
- `-C` → Target directory

✅ Result:
Files restored successfully.

---

### Subtask 3.2 — Verify Data Integrity

Compared original and restored files:

```bash
diff -r /home/user/Documents /home/user/RestoredDocuments
```

If no output appears → files are identical.

✅ Result:
No differences found. Data integrity verified.

---

## Key Security Concepts Learned

- Importance of data recovery planning
- Manual vs automated backups
- Cron job scheduling
- Archive compression with tar
- File integrity validation using diff
- Disaster Recovery fundamentals

---

## Security Impact

Before:
- No backup mechanism in place
- Risk of permanent data loss

After:
- Manual and automated backups configured
- Recovery process tested
- Data integrity verified
- Improved disaster readiness posture

---

## Conclusion

In this lab, I implemented manual and automated backup procedures using Linux tools. I successfully restored data from backup and verified its integrity. Understanding data recovery mechanisms strengthens disaster preparedness and ensures business continuity in real-world environments.
