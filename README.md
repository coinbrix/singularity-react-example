# React wrapper for Singularity SDK - singularity-react
You  can integrate singularity sdk to easy implement login flow and wallet integration

## Getting started

`$ npm install singularity-react --save`

### Mostly automatic installation

`$ react-native link singularity-react`

## SingularityListener

We emit below events to get callbacks. AddListener on eventEmitter  with name "SingularityListener"
```react-native
 this.eventEmitter.addListener("SingularityListener",(event)=>{
 const rsp=JSON.parse(JSON.stringify(event));
 rsp.eventType // you will get below events in eventType
 })
 ```
 
- onGetSingularityUserInfo
This event you get after successfully login. You will get the login user detail as json string in parameter.
You also get user detail anytime from shared preference using **SingularityUser** as key.
To get user detail from shared preference
```react-native
const user = await AsyncStorage.getItem("SingularityUser");// for ios it return map for android it return Json String
```

- onSingularityClose
This event you get when you click on close icon or press back button.


- onSingularityLogout
This event you get after successfully logout. It also delete user detail from shared preference.

- onSingularityError
This event you get when any Error occured

## startLogin
You can call this function to start login flow or can open profile page
  ###### key - provide user key as string
  ###### singularityConfig - provide configurations details as map, pass'environment' to set environment 0 for test 1 for production
  ```react-native
SingularityWrapper.startLogin(params);
  
```
  
  
  
