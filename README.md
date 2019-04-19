# React Native Navigation UI (in development)

Aiming to be highly customizable UI elements made for React Native with additional components specifically made for `react-native-navigation` by Wix!

Currently in development and code may change in the future!

##Installation

```
npm install react-native-vector-icons
npm install react-native-navigation-ui
react-native link react-native-vector-icons
```

##How to use components made for RNN?

You can register them like this
```
import { Navigation } from "react-native-navigation";
import { BottomSheets, Dialog, Snack } from "react-native-navigation-ui";

Navigation.registerComponent("bottom-sheets",() => BottomSheets);
Navigation.registerComponent("dialog",() => Dialog);
Navigation.registerComponent("snack",() => Snack);
```
And display them like this
```
Navigation.showOverlay({
    component: {
        name: "bottom-sheets",
        passProps: {
            title: "Remove file from storage?",
            sheets: [
                {
                    label: "Move to trash",
                    iconName: "delete",
                },
                {
                    label: "Cancel",
                    iconName: "close",
                }
            ],
            onPress: (index) => {
                alert(index);
            }
        }
    }
}).then();

 Navigation.showOverlay({
    component: {
        name: "dialog",
        passProps: {
            title: "Modal title!",
            description: "Write some description here!",
        }
    }
}).then();

Navigation.showOverlay({
    component: {
        name: "snack",
        passProps: {
            text: "Snack bar text",
            rightButton: {
                label: "Got it!",
                type: "cancel"
            }
        }
    }
}).then();
```

## Current available components

Component made for RNN will have star mark at the end.

- BottomSheets *
- Dialog *
- Snack *