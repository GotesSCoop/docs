**Hash de contrasenya per posar a /etc/shadow en Linux**

```
openssl passwd -1 -salt "$(cat /dev/urandom | head -n 1 | md5sum | head -c 8)"
o SHA-512:
python3 -c "import crypt;print(crypt.crypt(input('clear-text pw: '), crypt.mksalt(crypt.METHOD_SHA512)))"
```

**JSON pretty print**
```
cat fitxer.json | python -m json.tool
```

