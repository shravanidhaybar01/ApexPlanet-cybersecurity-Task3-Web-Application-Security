SQL Injection – Attack and Mitigation

Vulnerability

SQL Injection occurs when untrusted user input is included in SQL queries without proper parameterization.

Testing Environment

DVWA – Local Kali Linux lab.

Security Impact

- Unauthorized database access.
- Exposure of usernames and passwords.
- Unauthorized modification of database records.

Mitigation – Prepared Statements

Example PHP code using PDO:

<?php
$pdo = new PDO(
    "mysql:host=localhost;dbname=appdb;charset=utf8mb4",
    "appuser",
    "strong_password"
);

$username = $_POST['username'] ?? '';

$stmt = $pdo->prepare(
    "SELECT id, username FROM users WHERE username = :username"
);

$stmt->execute(['username' => $username]);

$result = $stmt->fetch(PDO::FETCH_ASSOC);
?>

The query uses a parameterized statement instead of directly concatenating user input.

Additional protections:

- Input validation.
- Least-privilege database accounts.
- Avoid exposing database error messages.

Conclusion

Prepared statements help prevent SQL Injection by separating SQL commands from user-supplied data.
