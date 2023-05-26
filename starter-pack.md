# Starter Pack

buat folder&#x20;

*   src

    * util
    * screen
    * component
    * api



### Folder util

buat file sebagai berikut

{% tabs %}
{% tab title="RootManager.js" %}
{% code fullWidth="true" %}
```javascript
import { createNativeStackNavigator } from "@react-navigation/native-stack";
import { NavigationContainer } from "@react-navigation/native";
import Splash from "../screen/Splash";
import Login from "../screen/Login";
import Home from "../screen/Home";
import Form from "../screen/Form";

const StackNavigation = createNativeStackNavigator();
const RootManager = () => {
    return(
        <NavigationContainer>
            <StackNavigation.Navigator initialRouteName="Aplikasi" screenOptions={{headerShown: false}}>
                <StackNavigation.Screen name="Splash" component={Splash} />
                <StackNavigation.Screen name="Login" component={Login} />
                <StackNavigation.Screen name="Home" component={Home} options={{headerShown: false }} />
                <StackNavigation.Screen name="Form" component={Form} />
            </StackNavigation.Navigator>
        </NavigationContainer>
    );
}

export default RootManager;
```
{% endcode %}
{% endtab %}

{% tab title="Helper.js" %}
```javascript
const routeApi = {
    login: 'auth/login',
    list_karyawan: 'main/list_karyawan',
    detail_karyawan: 'main/detail_karyawan',
    add_karyawan: 'main/add_karyawan',
    update_karyawan: 'main/update_karyawan',
    delete_karyawan: 'main/delete_karyawan',
  };
  const baseURL = 'https://gmedia.bz/DemoCase/';

  let sessionKey = '@session';

  export { routeApi, baseURL, sessionKey };
```
{% endtab %}

{% tab title="MessageUtil.js" %}
```javascript
import { showMessage } from "react-native-flash-message";

const MessageUtil = {
    showSuccess: (description) => {
        showMessage({
            message: "Berhasil",
            description: description,
            type: "success",
            color: "white",
            icon: "success"
        })
    },
    showWarning: (description) => {
        showMessage({
            message: "Warning",
            description: description,
            type: "warning",
            color: "white",
            icon: "warning"
        })
    },
    showFailed: (description) => {
        showMessage({
            message: "Failed",
            description: description,
            type: "danger",
            color: "white",
            icon: "danger"
        })
    },
}

export default MessageUtil;
```
{% endtab %}

{% tab title="InitSession.js" %}
```javascript
import { MMKV } from "react-native-mmkv";

const initSession = new MMKV();

export { initSession };
```
{% endtab %}

{% tab title="Storage.js" %}
```javascript
import { initSession } from "./InitSession";

const Storage = {
    StoreAsObject: (key, value) => {
        try {
          const jsonValue = JSON.stringify(value);
          initSession.set(key, jsonValue);
        } catch (e) {
          console.log(e);
          console.log('Saving Error');
        }
      },
      GetAsObject: (key) => {
        try {
          const jsonValue = initSession.getString(key);
          return jsonValue != null ? JSON.parse(jsonValue) : null;
        } catch (e) {
          console.log(e);
        }
      },
    RemoveValue: (key) => {
        try {
            initSession.delete(key);
          } catch (e) {
            console.log('key delete error :', e);
          }      
    }
}
export {Storage};

```
{% endtab %}
{% endtabs %}

### Folder Component

buat file sebagai berikut

{% tabs %}
{% tab title="First Tab" %}

{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

