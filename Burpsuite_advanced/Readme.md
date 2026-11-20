File Inclusion – Attack and Mitigation

Vulnerability

File Inclusion vulnerabilities occur when applications allow unsafe file paths or user-controlled file names to be included.

Types

1. Local File Inclusion (LFI).
2. Remote File Inclusion (RFI).

Security Impact

- Unauthorized access to local files.
- Exposure of configuration information.
- Potential remote code execution in vulnerable configurations.

Mitigation

1. Use an allowlist of permitted files.
2. Avoid directly passing user input to include() or require().
3. Disable remote file inclusion.
4. Restrict file system permissions.
5. Store sensitive files outside the web root.

Example secure PHP approach:

<?php

$allowedPages = [
    'home' => 'home.php',
    'about' => 'about.php',
    'contact' => 'contact.php'
];

$page = $_GET['page'] ?? 'home';

if (!array_key_exists($page, $allowedPages)) {
    http_response_code(404);
    exit('Page not found');
}

require __DIR__ . '/pages/' . $allowedPages[$page];

?>

PHP configuration:

allow_url_include = Off

Conclusion

Allowlisting and restrictive file permissions help prevent unauthorized file inclusion.
