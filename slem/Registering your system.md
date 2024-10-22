# Registering your system
To register SUSE Linux Enterprise Micro with SUSE Customer Center, run `transactional-update register` as follows:
```
transactional-update register -r REGISTRATION_CODE -e EMAIL_ADDRESS
```

To register with a local registration server, additionally specify the URL to the server:
```
transactional-update register -r REGISTRATION_CODE -e EMAIL_ADDRESS \
--url "https://suse_register.example.com/"
```
