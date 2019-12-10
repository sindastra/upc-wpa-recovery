# UPC WPA PSK recovery tool

Recover WPA passphrase for UPCXXXXXXX access points

This repo hosts a copy of https://haxx.in/upc_keys.c for archiving purposes.

# Compiling

    gcc -O2 -o upc_keys upc_keys.c -lcrypto

# Compiling to be portable (static linking)
    gcc -static -O2 -o upc_keys upc_keys.c -lcrypto
