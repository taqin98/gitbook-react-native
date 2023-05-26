# Update Karyawan

{% swagger method="post" path="" baseUrl="https://gmedia.bz/DemoCase/main/update_karyawan" summary="" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Client-Service" %}
gmedia-recruitment
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Auth-Key" %}
demo-admin
{% endswagger-parameter %}

{% swagger-parameter in="header" name="User-Id" %}
id dari success login
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Token" %}
token dari success login
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nip" %}
34234
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nama" %}
Joko Satoru
{% endswagger-parameter %}

{% swagger-parameter in="body" name="alamat" %}
Bandung
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" %}
L
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tgl_lahir" %}
2023-05-27
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
  "response": [],
  "metadata": {
    "status": 200,
    "message": "Berhasil memperbarui data"
  }
}
```
{% endswagger-response %}
{% endswagger %}
