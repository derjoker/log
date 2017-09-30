# rnxx
react-native-xx

## 2017.08.30

### remote submit (redux-form)
* [doc](https://redux-form.com/7.0.4/examples/remotesubmit/)
* [github](https://github.com/erikras/redux-form/tree/master/examples/remoteSubmit)

### withNavigation (Context)
```
// MyContainer.js

const MyComponent = ({ dispatch, navigation }) => (
  <Component ... />
)

MyComponent.propTypes = {
  dispatch: PropTypes.func.isRequired, // redux (connect)
  navigation: PropTypes.func.isRequired, // react-navigation (withNavigation)
}

export default withNavigation(connect()(MyComponent))
```

### [withNavigation does not provide valid navigation object #329](https://github.com/react-community/react-navigation/issues/329)
* [answer from joncursi](https://github.com/react-community/react-navigation/issues/329#issuecomment-293257042)

### RouteConfigs (navigationOptions)
```
const EditDoneComponent = ({ dispatch, navigation }) => (
  <Button title="Done" onPress={() => {
    dispatch(action_submit);
    navigation.goBack();
  }} />
)

const EditDoneContainer = withNavigation(connect()(EditDoneComponent))

StackNavigator({
  Edit: { screen: EditScreen, navigationOptions: ({ navigation }) => {
    title: `${navigation.state.params.title}`,
    headerRight: (
      <EditDoneContainer />
    )
  } }
})
```
