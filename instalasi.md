# Instalasi

### Membuat proyek baru

```atom
npx react-native@latest init AwesomeProject
```

### Open VSCode

Buka folder proyek yg telah dibuat menggunakan VSCode Editor.

Install extensions tambahan untuk VSCode

<div align="left" data-full-width="true">

<figure><img src=".gitbook/assets/Screen Shot 2023-05-25 at 4.36.26 PM.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src=".gitbook/assets/Screen Shot 2023-05-25 at 4.36.32 PM.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src=".gitbook/assets/Screen Shot 2023-05-25 at 4.36.38 PM.png" alt=""><figcaption></figcaption></figure>

</div>

<div align="left">

<figure><img src=".gitbook/assets/Screen Shot 2023-05-25 at 4.36.44 PM.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src=".gitbook/assets/Screen Shot 2023-05-25 at 4.36.59 PM.png" alt=""><figcaption></figcaption></figure>

</div>

### Run Android

Pasang device android ke Laptop/PC, Buka Terminal

```
npm run android
```

### Install Library

```
npm install namalib namalib2 namalib3 namalib4
```

{% tabs %}
{% tab title="First Tab" %}
@react-native-community/datetimepicker @react-navigation/native @react-navigation/native-stack @rneui/base @rneui/themed moment react-native-dropdown-picker react-native-flash-message react-native-mmkv react-native-safe-area-context react-native-screens react-native-vector-icons

&#x20;
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

### Setting React Native Navigation

Edit `MainActivity.java`&#x20;

`lokasi : android/app/src/main/java/<your package name>/MainActivity.java`

```java
public class MainActivity extends ReactActivity {
  // ...
  @Override
  protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(null);
  }
  // ...
}


```
