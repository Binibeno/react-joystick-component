## React Joystick Component

[![Build Status](https://travis-ci.org/elmarti/react-joystick-component.svg?branch=master)](https://travis-ci.org/elmarti/react-joystick-component)

[Click here to see examples](https://elmarti.github.io/react-joystick-component/)

```
npm i react-joystick-component --save
```

```
import { Joystick } from 'react-joystick-component';
```


```React
<Joystick size={100} sticky={true} baseColor="red" stickColor="blue" move={handleMove} stop={handleStop}></Joystick>
```

Component Props - as described by IJoystickProps

| Prop  | Type  | Description  |
|---|---|---|
| size  |  number |  The size in px of the Joystick base  |
|  baseColor |  string |  The color of the Joystick base |
| stickColor  |  string |  The color of the Stick |
|  throttle | number  |  The [throttling](https://codeburst.io/throttling-and-debouncing-in-javascript-b01cad5c8edf) rate of the move callback |
| sticky | Boolean | Should the joystick stay where it is when the interaction ends |
| stickImage | string | The image to be shown for the joystick |
| baseImage | string | The image to be shown for the pad |
| followCursor | Boolean | Make the stick follow the cursor position |
|  move | Function  | Callback fired on every mouse move, not throttled unless a throttling rate is provided as above  |
|  stop | Function  | Callback fired when the user releases the joystick  |
| start  |  Function | Callback fired when the user starts moving the Joystick  |
| disabled | Boolean | When true, block any usage of the Joystick. This will also apply the `joystick-disabled` and `joystick-base-disabled` classNames  |

```TypeScript
interface IJoystickProps {
    size?: number;
    baseColor?: string;
    stickColor?: string;
    disabled?: boolean;
    throttle?: number;
    sticky?: boolean;
    stickImage?: string;
    baseImage?: string;
    followCursor?: boolean;
    move?: (event: IJoystickUpdateEvent) => void;
    stop?: (event: IJoystickUpdateEvent) => void;
    start?: (event: IJoystickUpdateEvent) => void;
}
```

```TypeScript
type JoystickDirection = "FORWARD" | "RIGHT" | "LEFT" | "BACKWARD";

export interface IJoystickUpdateEvent {
    type: "move" | "stop" | "start";
    x: number | null;
    y: number | null;
    direction: JoystickDirection | null;
}
```
