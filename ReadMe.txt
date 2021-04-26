Requirements:

    * openssl
    * base32 (maybe from GNU coreutils)

You are recommended to use it with "pass" from https://www.passwordstore.org/

For example, to get the token for two-factor authentication:

    # Usage: totp [server] [interval] [timestamp] < secret
    pass show otp/GitHub | totp GitHub

    # Run this at Fri Jan 1 00:00:00 UTC 2038 you'd get 846121.
    echo "base32-decoded secret" | base32 | totp GitHub 30 #2145916800

In the first example above, the second parameter "GitHub" is optional, and
defaults to "Google", since the Google Authenticator app has become the de
facto standard for such usage.
