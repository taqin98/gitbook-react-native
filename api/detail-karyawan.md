# Detail Karyawan

{% swagger method="post" path="" baseUrl="https://gmedia.bz/DemoCase/main/detail_karyawan" summary="" expanded="true" %}
{% swagger-description %}
**Webservice untuk menampilkan detail karyawan yang telah tersimpan**
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
nip dari karyawan yang telah tersimpan
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
  "response": {
    "nip": "20210001",
    "nama": "Demo Tester 1",
    "alamat": "Jl. Mangga 5, Semarang - Edited",
    "gender": "L",
    "tgl_lahir": "01-05-1995"
  },
  "metadata": {
    "status": 200,
    "message": "Berhasil"
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
    "message": "Data not found"
  }
}
```
{% endswagger-response %}
{% endswagger %}
