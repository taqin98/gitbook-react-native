# Auth

{% swagger method="post" path="" baseUrl="https://gmedia.bz/DemoCase/auth/login" summary="" expanded="true" %}
{% swagger-description %}
**Websevice ini digunakan untuk login kedalam aplikasi**
{% endswagger-description %}

{% swagger-parameter in="header" name="Client-Service" %}
gmedia-recruitment
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Auth-Key" %}
demo-admin
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" %}
admindata
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" %}
12345
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
  "response": {
    "uid": "1",
    "token": "8godoajVqNNOFz21npycK6iofUgFXl1kluEJt/WYFts9C8IZqUOf7rOXCe0m4f9B"
  },
  "metadata": {
    "status": 200,
    "message": "Login berhasil"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```json
{
  "response": [],
  "metadata": {
    "status": 400,
    "message": "Username & Password harus diisi"
  }
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```json
{
  "response": [],
  "metadata": {
    "status": 404,
    "message": "Username / Password salah"
  }
}
```
{% endswagger-response %}
{% endswagger %}
