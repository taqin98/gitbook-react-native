# List Karyawan

{% swagger method="post" path="" baseUrl="https://gmedia.bz/DemoCase/main/list_karyawan" summary="" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Client-Service" %}
gmedia-recruitment
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Auth-Key" %}
demo-admin
{% endswagger-parameter %}

{% swagger-parameter in="header" name="User-Id" %}
id user diambil dari response success login
{% endswagger-parameter %}

{% swagger-parameter in="body" name="start" required="false" %}
index pertama yang akan di tampilan di aplikasi


{% endswagger-parameter %}

{% swagger-parameter in="body" name="count" required="false" %}
jumlah data yang akan di tampilan di aplikasi
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Token" %}
token user diambil dari response success login
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```jsonp
{
  "response": [
    {
      "nip": "20210004",
      "nama": "Demo Tester 4",
      "alamat": "Jl. Belimbing 5, Semarang"
    },
    {
      "nip": "20210003",
      "nama": "Demo Tester 3",
      "alamat": "Jl. Durian 5, Semarang"
    },
    {
      "nip": "20210002",
      "nama": "Demo Tester 2",
      "alamat": "Jl. Manggis 5, Semarang"
    },
    {
      "nip": "20210001",
      "nama": "Demo Tester 1",
      "alamat": "Jl. Mangga 5, Semarang - Edited"
    }
  ],
  "metadata": {
    "status": 200,
    "message": "Berhasil"
  }
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```json5
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
