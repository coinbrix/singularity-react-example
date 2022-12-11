# Singularity-iOS
You  can integrate singularity sdk to easy implement login flow and wallet integration

## Integration

###### Pod
Add below line in your podflie
```ruby
pod "Singularity-iOS"
```
###### SPM
you can add on SPM using below link
##### https://github.com/coinbrix/Singularity-iOS

## SingularityListener

Implement this protocol to get callbacks

- onGetSingularityUserInfo
This callback you get after successfully login. You will get the login user detail as json string in parameter.
You also get user detail anytime from shared preference using **SingularityUser** as key.
```swift
    func onGetSingularityUserInfo(user: [String:Any]) {
   
  }
```
To get user detail from UserDefaults
```swift
let prefs = UserDefaults.standard
let user = prefs.object(forKey: "SingularityUser") 
```

- onSingularityClose
This callback you get when you click on close icon or press back button.
```swift
    func onSingularityClose() {
   
  }
```

- onSingularityLogout
This callback you get after successfully logout. It also delete user detail from shared preference.
```swift
    func onSingularityLogout() {
  
  }
```

- onSingularityError
This callback you get if any error occured in initalization. It provides error message and error code.
```swift
    func onSingularityError(message: String, code: Int) {
  
  }
```

## SingularitySDKInitializer - startLogin
You can call this function to start login flow or can open profile page
  ###### params - provide params needed for initalization- a key and environment (test/production) is compulsory
  ###### listener - provide SingularityListener to recieve callbacks
  ###### parentVC - provide a UIViewController in which we can present our login screen
  ```swift
SingularitySDKInitializer.startLogin(on parentVC: <UIViewController>,
                                  with params: <SingularityParams>,
                                  listener: <SingularityListener>)
  
```
  
  
  
