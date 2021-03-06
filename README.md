# capacitor-start-navigation [![npm version](https://badge.fury.io/js/%40proteansoftware%2Fcapacitor-start-navigation.svg)](https://badge.fury.io/js/%40proteansoftware%2Fcapacitor-start-navigation)

Capacitor plugin that allows your app to start native navigation


## API

| method            | info                                          | platform    |
| ----------------- | --------------------------------------------- | ----------- |
| `launchMapsApp`     | Launches native maps with navigation started.                        | ios/android |


## Usage

```ts
import { Plugins } from "@capacitor/core";
const { StartNavigationPlugin } = Plugins;

//
// with type support
import { StartNavigationPlugin } from "@proteansoftware/capacitor-start-navigation";
const startNavigation = new StartNavigationPlugin();

//
// alternatively - without types
const { StartNavigationPlugin } = Plugins;

//
// launches native maps with directions to Warwick, UK
StartNavigationPlugin.launchMapsApp({
  latitude: 52.28333,
  longitude: -1.58333,
  name: "Example location"
});

```

## iOS setup

- `sudo gem install cocoapods` _(once a time)_
- `ionic start my-cap-app --capacitor`
- `cd my-cap-app`
- `mkdir www && touch www/index.html`
- `npx cap add ios`
- `npm install --save @proteansoftware/capacitor-start-navigation`
- `npx cap sync ios` _(always do sync after a plugin install)_
- `npx cap open ios`

## Android setup

- `ionic start my-cap-app --capacitor`
- `cd my-cap-app`
- `mkdir www && touch www/index.html`
- `npx cap add android`
- `npm install --save @proteansoftware/capacitor-start-navigation`
- `npx cap sync android` _(always do sync after a plugin install)_
- `npx cap open android`
- `[extra step]` in android case we need to tell Capacitor to initialise the plugin:

> on your `MainActivity.java` file add `import com.servicesight.capacitor.startnavigation.StartNavigationPlugin;
` and then inside the init callback `add(StartNavigationPlugin.class);`

Now you should be set to go. Try to run your client using `ionic cap run android --livereload`.

## License

MIT