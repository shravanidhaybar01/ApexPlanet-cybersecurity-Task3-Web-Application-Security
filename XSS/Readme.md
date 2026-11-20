Cross-Site Scripting (XSS) – Attack and Mitigation

Vulnerability

XSS occurs when untrusted content is interpreted as executable JavaScript in a user's browser.

Types Tested

1. Stored XSS.
2. Reflected XSS.

Security Impact

- Session theft under vulnerable conditions.
- Unauthorized actions in a user's browser.
- Malicious content execution.

Mitigation – PHP Output Encoding

<?php
$userInput = $_GET['name'] ?? '';

$safeOutput = htmlspecialchars(
    $userInput,
    ENT_QUOTES | ENT_SUBSTITUTE,
    'UTF-8'
);

echo $safeOutput;
?>

Additional protections:

- Context-aware output encoding.
- Input validation.
- Content Security Policy.
- HttpOnly and Secure session cookies.

Conclusion

Output encoding helps ensure that untrusted input is displayed as data instead of being executed as JavaScript.
