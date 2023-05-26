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
{% tab title="Header.js" %}
```javascript
import {Text} from '@rneui/base';
import React from 'react';
import {StyleSheet, TouchableOpacity, View} from 'react-native';
import FontAwesome from "react-native-vector-icons/FontAwesome";

const Header = props => {
  return (
    <View style={style.container}>
      <View
        style={{
          margin: 10,
          flex: 1,
          flexDirection: "row",
          alignItems: 'center',
        }}>
        {
          props.buttonBack && 
          <TouchableOpacity style={{
              marginRight: 20
          }} onPress={
              () =>  { props.navigation.goBack() }
          }>
              <FontAwesome name="arrow-left" size={30} />
          </TouchableOpacity>
        }
        
        <Text style={[style.textContainer, { flex : props.buttonLogout ? 1 : 0.5 }]}>{props.label}</Text>

        {
          props.buttonLogout && 
          <TouchableOpacity style={{
              marginRight: 20
          }} onPress={
              () =>  { props.clickLogout() }
          }>
              <FontAwesome sty name="arrow-left" size={30} />
          </TouchableOpacity>
        }
      </View>
    </View>
  );
};

const style = StyleSheet.create({
  container: {
    height: 55,
    borderWidth: 1,
    paddingLeft: 20,
    paddingTop: 0,
    backgroundColor: "green",
  },
  textContainer: {
    color: "white",
  },
});

export default Header;
```
{% endtab %}

{% tab title="FormControl.js" %}
```javascript
import React from 'react';
import {Image} from '@rneui/base';
import {Input} from '@rneui/themed';
import {StyleSheet, TouchableOpacity, View} from 'react-native';

const FormControl = props => {
  return (
    <View style={style.containerInput}>
      <View style={style.containerGroup}>
        <Input
          placeholder={props.placeholder}
          value={props.value}
          inputStyle={style.inputStyle}
          containerStyle={style.customStyleInput}
          inputContainerStyle={style.inputCustomContainer}
          onChangeText={txt => {
            console.log('txt', txt);
            props.changeValue(txt);
          }}
          secureTextEntry={props.isSecure == true ? props.secureText : false}
        />
      </View>
      {props.isSecure && (
        <TouchableOpacity
          onPress={() => {
            props.changeSecure();
          }}>
          <Image
            source={{
              uri: 'https://images.unsplash.com/photo-1611162618828-bc409f073cbf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80',
            }}
            style={{height: 30, width: 30}}
          />
        </TouchableOpacity>
      )}
    </View>
  );
};

const style = StyleSheet.create({
  containerInput: {
    backgroundColor: 'yellow',
    height: 55,
    justifyContent: 'center',
    borderRadius: 8,
    alignItems: 'center',
    flexDirection: 'row',
    paddingStart: 10,
    paddingEnd: 10,
    marginTop: 20,
    marginStart: 24,
    marginEnd: 24,
  },
  inputCustomContainer: {
    borderColor: 'transparent',
    height: 55,
    justifyContent: 'center',
    alignItems: 'center',
  },
  inputStyle: {
    fontSize: 14,
    color: 'black',
    textAlignVertical: 'center',
    // fontFamily: 'Arial',
  },
  customStyleInput: {
    height: 55,
  },
  containerGroup: {
    flex: 1,
  },
});

export default FormControl;
```
{% endtab %}

{% tab title="ButtonControl.js" %}
```javascript
import React from 'react';
import { Text} from '@rneui/base';
import { TouchableOpacity, StyleSheet} from 'react-native';

const ButtonControl = props => {
  return (
    <TouchableOpacity
      onPress={() => {
        props.onPress();
      }}
      style={[
        style.container,
        {
          marginStart: props.marginStart,
          marginEnd: props.marginEnd,
          backgroundColor: props.backgroundColor,
        },
      ]}>
      <Text
        style={[
          style.text,
          {
            color: props.textColor,
            fontSize: props.fontSize,
          },
        ]}>
        {props.label}
      </Text>
    </TouchableOpacity>
  );
};

const style = StyleSheet.create({
  container: {
    height: 45,
    justifyContent: 'center',
    alignItems: 'center',
    borderRadius: 8,
    marginTop: 20,
  },
  text: {
    fontWeight: 'bold',
  },
});

export default ButtonControl;
```
{% endtab %}

{% tab title="DatePickerControl.js" %}
```javascript
import { DateTimePickerAndroid } from "@react-native-community/datetimepicker";
import React from "react";
import { View } from "react-native";

const DatePickerControl = () => {
    return(
        <View>
        <DateTimePickerAndroid />
        </View>
    );
}
```
{% endtab %}

{% tab title="DropdownControl.js" %}
```javascript
import React, { useState } from 'react';
import {StyleSheet, View} from 'react-native';
import DropDownPicker from 'react-native-dropdown-picker';

const DropdownControl = props => {
    const [open, setOpen] = useState(false);
  const aList = [
    {label: 'Laki-Laki', value: 'L'},
    {label: 'Perempuan', value: 'P'},
  ];
  return (
    <View style={style.container}>
      <DropDownPicker items={aList} 
      value={props.value}
      setValue={ txt => props.setValue(txt) }
      open={open} 
      setOpen={setOpen} 
        style={style.dropdownStyle}
        dropDownContainerStyle={style.dropdownStyle}
      />
    </View>
  );
};

const style = StyleSheet.create({
    container: {
        margin: 20,
        backgroundColor: 'yellow',
        zIndex: 999
    },
    dropdownStyle: {
        backgroundColor: 'yellow',
        borderColor: 'transparent'
    },
})

export default DropdownControl;
```
{% endtab %}
{% endtabs %}

### Folder api

buat file sebagai berikut

{% tabs %}
{% tab title="ApiManager.js" %}
```javascript
import { baseURL, sessionKey  } from '../util/Helper';
import { Storage } from '../util/Storage';

const ApiManager = async (metode, params, url) => {
    const sesi = Storage.GetAsObject(sessionKey);

    let headers = {
        'Client-Service': 'gmedia-recruitment',
        'Auth-Key': 'demo-admin',
        'Content-Type': 'application/json',
    };

    if (sesi != null || sesi != undefined){
        headers['Token'] = sesi.token;
        headers['User-id'] = sesi.uid;
    }
    
    console.log('sesi', sesi);

    const dataRes = await fetch(`${baseURL}${url}`, {
        method: metode,
        headers: headers,
        body: JSON.stringify(params)
    });

    // console.log(dataRes, 'datares');
    return dataRes.json().then( data => data).catch(err => err);
}

export { ApiManager };java
```
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

