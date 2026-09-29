$ echo "=== SUDO? ==="; sudo -n true 2>&1 && echo "SUDO OK" || echo "NO SUDO"; echo "=== NETWORK TEST (npm registry) ==="; curl -sI --max-time 10 https://registry.npmjs.org/ | head -3; echo "=== NETWORK TEST (github) ==="; curl -sI --max-time 10 https://github.com | head -3; echo "=== BANDWIDTH (download 5MB from npm) ==="; time curl -s --max-time 25 -o /tmp/speedtest.bin https://registry.npmjs.org/typescript/-/typescript-5.5.4.tgz && ls -la /tmp/speedtest.bin=== SUDO? ===
SUDO OK
=== NETWORK TEST (npm registry) ===
HTTP/2 200 
date: Tue, 29 Sep 2026 14:42:19 GMT
content-type: application/json
=== NETWORK TEST (github) ===
HTTP/2 200 
cache-control: max-age=0, private, must-revalidate
content-language: en-US
=== BANDWIDTH (download 5MB from npm) ===
-rw-r--r-- 1 user user 4043150 Sep 29 14:42 /tmp/speedtest.bin
real	0m0.173s
user	0m0.051s
sys	0m0.016s
