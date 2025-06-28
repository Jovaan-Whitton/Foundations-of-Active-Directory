#  Active Directory Commands with Explanations

##  User & Group Enumeration

- `net user /domain`
  > Lists all user accounts in the domain.

- `net group /domain`
  > Lists all groups in the domain.

- `whoami /all`
  > Displays current user and associated privileges and group memberships.

- `dsquery user`
  > Queries the directory for user objects (requires elevated permissions).

- `net localgroup administrators`
  > Shows the local machine's admin group members.

##  Domain Controller Discovery

- `nltest /dclist:yourdomain.local`
  > Lists the domain controllers for the specified domain.

- `echo %logonserver%`
  > Shows which domain controller authenticated your session.

