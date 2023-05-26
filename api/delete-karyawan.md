# Delete Karyawan

{% swagger method="post" path="" baseUrl="https://gmedia.bz/DemoCase/main/delete_karyawan" summary="" expanded="true" %}
{% swagger-description %}
**Webservice ini digunakan untuk menghapus data karyawan yang telah tersimpan**
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

{% swagger-response status="200: OK" description="" %}
```json
{
  "response": [],
  "metadata": {
    "status": 200,
    "message": "Berhasil menghapus data"
  }
}
```
{% endswagger-response %}
{% endswagger %}
