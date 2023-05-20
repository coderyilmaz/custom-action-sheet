# custom-action-sheet

The `custom-action-sheet` component is a cross-platform ActionSheet component that provides a unified way to display ActionSheets on iOS and Android. It utilizes the native `ActionSheetIOS` component on iOS for optimal visual effects.

# Note

This is an updated and enhanced version of the original "react-native-actionsheet" library. In this new version, existing issues have been addressed, and the library is now compatible with newer versions of React Native.

Note: This library includes improvements made on top of the original "beefe/react-native-actionsheet" repository.

Users can seamlessly integrate the ActionSheet component using this updated version and incorporate it into their projects with ease.

## Installation

```bash
npm install custom-action-sheet --save
```

## Usage

```javascript
import ActionSheet from 'custom-action-sheet';

class Demo extends React.Component {
  showActionSheet = () => {
    this.ActionSheet.show();
  };

  render() {
    return (
      <View>
        <Text onPress={this.showActionSheet}>Open ActionSheet</Text>
        <ActionSheet
          ref={o => (this.ActionSheet = o)}
          title={'Which one do you like?'}
          options={['Apple', 'Banana', 'cancel']}
          cancelButtonIndex={2}
          destructiveButtonIndex={1}
          onPress={index => {
            /* do something */
          }}
        />
      </View>
    );
  }
}
```

### Using ActionSheetCustom directly

You can also use the `ActionSheetCustom` component directly to customize the options and title.

```javascript
import { ActionSheetCustom as ActionSheet } from 'custom-action-sheet';

const options = [
  'Cancel',
  'Apple',
  <Text style={{ color: 'yellow' }}>Banana</Text>,
  'Watermelon',
  <Text style={{ color: 'red' }}>Durian</Text>,
];

class Demo extends React.Component {
  showActionSheet = () => {
    this.ActionSheet.show();
  };

  render() {
    return (
      <View>
        <Text onPress={this.showActionSheet}>Open ActionSheet</Text>
        <ActionSheet
          ref={o => (this.ActionSheet = o)}
          title={<Text style={{ color: '#000', fontSize: 18 }}>Which one do you like?</Text>}
          options={options}
          cancelButtonIndex={0}
          destructiveButtonIndex={4}
          onPress={index => {
            /* do something */
          }}
        />
      </View>
    );
  }
}
```

## Customizing Styles

You can customize the style of the ActionSheet by providing a `styles` prop. The default styles are defined in `lib/styles.js`. See the example below:

```javascript
const styles = {
  titleBox: {
    background: 'pink',
  },
  titleText: {
    fontSize: 16,
    color: '#000',
  },
};

<ActionSheet
  // ...
  styles={styles}
/>
```

## Props

- `title`: PropTypes.string or PropTypes.element
- `message`: PropTypes.string or PropTypes.element
- `options`: PropTypes.arrayOf([PropTypes.string, PropTypes.element])
- `tintColor`: PropTypes.string
- `cancelButtonIndex`: PropTypes.number
- `destructiveButtonIndex`: PropTypes.number
- `onPress`: PropTypes.func (index) => {}
- `styles` (only for `ActionSheetCustom`): {}

For more details on props, please refer to the [options.js](https://github.com/coderyilmaz/custom-action-sheet/blob/main/lib/options.js) file.
