# Crypto link

The application supports encrypted links. A link can be encrypted using an RSA-1024 or RSA-4096 key. Typically, an RSA-1024 key is used, but if the link exceeds 110 characters, an RSA-4096 key will be employed.

Link encryption is designed to conceal the subscription address from the user. Once an encrypted subscription is added, the user cannot edit, view, or share server configurations contained in the subscription. The encryption keys themselves are securely embedded in the application, ensuring that subscription data remains protected.

***

You can encrypt a link in three ways:

1. Using this [web page](https://crypto.happ.su)
2. Using the [API](crypto-link.md#api-instructions)
3. Using RSA [keys](crypto-link.md#rsa-keys)

#### API Instructions

To use the API, you need to send a request to the following address: `https://crypto.happ.su/api.php`

**Example:**

```bash
curl -X POST -H "Content-Type: application/json" -d '{"url":"https://your_url.com"}' "https://crypto.happ.su/api.php"
```

This will return the encrypted version of your link, which can be used in the application.

#### RSA Keys

If you prefer to encrypt the link manually, you can use the provided RSA keys.

**RSA Key (RSA-1024):**

```
-----BEGIN PUBLIC KEY-----
MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCxsS7PUq1biQlVD92rf6eXKr9o
G1/SrYx3qWahZP+Jq35m4Wb/Z+mB6eBWrPzJ/zZpZLWLQorcvOKt+sLaCHyH1HLN
kti4jlaEQX6x97XgBm8GK08+lLLWquFDhWRNxsrfzJyNdpVopzBRmCJKTc8ObYyP
brv9T35a8Kd5WqjnUwIDAQAB
-----END PUBLIC KEY-----
```

**RSA Key (RSA-4096):**

```
-----BEGIN PUBLIC KEY-----
MIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEA5cL2yu9dZGnNbs4jt222
NugIqiuZdXKdTh4IgXZmOX0vdpW+rYWrPd1EObQ3Urt+YBTK5Di98EBjYCPr8tus
aVRAn3Vaq41CDisEdX35u1N8jSHQ0zDOtPdrvJtlqShib4UI6Vybk/QSmoZVbpRb
67TNsiFqBmK1kxT+mbtHkhdT2u+hzNLQr0FtJR1+gC+ELKZ48zZY/d3YSSRSb+dx
Und4FH31Kz68VKqlajISSzIrGQWc/zqSlihIvfnTPNX3pCyJpwAuYXieWSRDAogr
wGwoiN++y14OLYHrNlqzoJ44WM3Tbm7x1Dj/8QI3tzwixli/0JmqQ19ssETDbVQ9
0asoPc4QFhyc4c+PH62AdK1S+ysXt5uqEujRBk3rC53l65IOVXSTZgsLwzS7EFY9
lZszJXUJJh5GB9heO8c7PNCTOxno3l4684iHFJuxnkS0DLbdzCXfovwfIP8q3lj7
UJswPKVHkCLNSUutNke+xex1J3YEdvebJzv7Dk78PqLRmLWaEsAhQanXs93aTxEk
d/p7hgFV30QozVQ/oNAvmQSVIBd6zCGM3of3R3tmDkDNGQGrY4MBTX+cTJGYstdh
QXxj1oFZEG16F/0GGXG+sia67gYM3OC7RWyBOzULsEmupIiM8Vdx1iErw7yvJSC4
IsIsWZD8JAmZtLBqEQ/TvfcCAwEAAQ==
-----END PUBLIC KEY-----
```

Use these keys to encrypt your links with your preferred RSA encryption tool.

