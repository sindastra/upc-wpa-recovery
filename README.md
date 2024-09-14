# UPC WPA PSK recovery tool

Recover WPA passphrase for UPCXXXXXXX access points

This repo hosts a copy of https://haxx.in/upc_keys.c for archiving purposes.

# Compiling

    gcc -O2 -o upc_keys upc_keys.c -lcrypto

# Compiling to be portable (static linking)
    gcc -static -O2 -o upc_keys upc_keys.c -lcrypto

# Compiling x86-32 on x86-64 (Debian/Ubuntu)
Make sure to install ```gcc-multilib``` and ```libssl-dev:i386``` and then compile with

    gcc -m32 -static -O2 -o upc_keys upc_keys.c -lcrypto

# Cross-compiling for Windows (Debian/Ubuntu)
Make sure to install ```gcc-mingw-w64``` and the OpenSSL library then compile with

    i686-w64-mingw32-gcc -static -O2 -o upc_keys.exe upc_keys.c -lcrypto

# Compiling universal binary on macOS (MacPorts)

    sudo port install openssl11 +universal
    clang -O3 -o upc_keys.x86_64 upc_keys.c -lcrypto -I/opt/local/include/openssl-1.1/ -L/opt/local/lib/openssl-1.1/ -target x86_64-apple-macos10.6
    clang -O3 -o upc_keys.arm64 upc_keys.c -lcrypto -I/opt/local/include/openssl-1.1/ -L/opt/local/lib/openssl-1.1/ -target arm64-apple-macos11
    lipo -create -output upc_keys.universal upc_keys.arm64 upc_keys.x86_64
