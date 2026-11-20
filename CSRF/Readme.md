Cross-Site Request Forgery (CSRF) – Attack and Mitigation

Vulnerability

CSRF tricks an authenticated user's browser into sending an unwanted request to a web application.

Security Impact

- Unauthorized password changes.
- Unauthorized account modifications.
- Unwanted actions using an authenticated session.

Mitigation – CSRF Token

Generate a token:

<?php
session_start();

if (empty($_SESSION['csrf_token'])) {
    $_SESSION['csrf_token'] = bin2hex(random_bytes(32));
}
?>

Add it to the form:

<input type="hidden"
       name="csrf_token"
       value="<?= htmlspecialchars($_SESSION['csrf_token'], ENT_QUOTES, 'UTF-8') ?>">

Validate it on the server:

<?php
session_start();

if (
    !isset($_POST['csrf_token']) ||
    !hash_equals(
        $_SESSION['csrf_token'] ?? '',
        $_POST['csrf_token']
    )
) {
    http_response_code(403);
    exit('Invalid CSRF token');
}
?>

Additional protections:

- SameSite cookies.
- Origin validation.
- Server-side token validation.
- Protection of every state-changing request.

Conclusion

CSRF tokens help ensure that state-changing requests originate from legitimate application forms.
