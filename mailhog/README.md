# how to send mail
```sh
curl --url 'smtp://localhost:1025' \
  --mail-from 'from@example.com' --mail-rcpt 'to@example.com' \
  --upload-file mail.txt
```