The eventer is a simple publish-subscribe messaging system. Unlike native CustomEvents, it doesn’t have to be called from a DOM element, but can be used anywhere in your code.

It allows triggering and listening to custom messages.

``` typescript
import { Eventer } from ‘entcore-toolkit’;

const eventer = new Eventer();
```

- Listen to an event

        eventer.on(‘myevent’, () => console.log(‘event’));

- Stop listening

        eventer.on(‘myevent’);

- Stop listening for a specific function

        const myFunc = () => console.log(‘f’);
        eventer.on(‘myevent’, myFunc);
        eventer.off(‘myevent’, myFunc);

- Listen only once

        eventer.once(‘myevent’, myFunc);

- Trigger event

        eventer.trigger(‘myevent’);

- Listen to an event with data

        eventer.on(‘myevent’, (data) => console.log(‘event’ + data.message));

- Trigger event with data

        eventer.trigger(‘myevent’, {“message” : “hello !”});
