# Onboarding Tutorial Screen

The Onboarding Tutorial Screen is a ReactNative based onboarding screen. It can be configured to have 1 or many
slide screens with content and expansion detailed in the file.

## Installation

After you have added the screen module into your project, you will need to configure a few items by modifying the project
files in the github repository. Please note to replace ####### with the numeric sequence for your screen (found in folder name under /src/features) and also that the @BluePrint tags for ImportInsertion and NavigationInsertion will be removed in future so placement is with other imports and inside the AppNavigator above other screens.

### STEP 1: Add dependency library to the project.

**/PROJECT_ROOT_DIRECTORY/package.json:**

**ADD** dependencies by updating the `package.json` and inserting the following after the dependencies opening line "_"dependencies": {_ ":

`"react-native-app-intro-slider": "^4.0.4", `

### Step 2: Add screen into your project screen navigation.

**/src/mainNavigator.js:**
**ADD** immediately below in the section labeled //@BlueprintImportInsertion:

`import Onboarding from '../features/Onboarding#######/';`

**ADD** immediately below in the section inside AppNavigator definition labeled //@BlueprintNavigationInsertion section:

`Onboarding#######: { screen: Onboarding.navigator },`


### STEP 3: Update the Onboarding Slide Screen content as desired, the navigated screen after done (typically the HOME screen) including the number of slide screens needed.

**/src/features/Onboarding#######/slides.js:**

**MODIFY** slides, update with your slides content/desired number of slides:

```
const slides = [
 {
   key: 'one',
   title: 'Title 1',
   text: 'Description.\nSay something cool',
   image: { uri: "https://crowdbotics-slack-dev.s3.amazonaws.com/media/project_component_resources/cb-icon.png" },
   backgroundColor: '#59b2ab',
 },
 {
   key: 'two',
   title: 'Title 2',
   text: 'Other cool stuff',
   image: { uri: "https://crowdbotics-slack-dev.s3.amazonaws.com/media/project_component_resources/cb-icon.png" },
   backgroundColor: '#febe29',
 },
 // {
 //   key: 'three',
 //   title: 'Rocket guy',
 //   text: 'I\'m already out of descriptions\n\nLorem ipsum bla bla bla',
 //   image: require('./assets/3.jpg'),
 //   backgroundColor: '#22bcb5',
 // }
];
```
**/src/features/Onboarding#######/index.js:**

**MODIFY** the value of `REDIRECT_SCREEN_NAME` with the name of the screen you would like onbarding to redirect to (same name as defined in `mainNavigator`):

```js
const REDIRECT_SCREEN_NAME = 'LoginAndSignup177769' // name of your screen to redirect
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)