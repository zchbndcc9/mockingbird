# mockingbird
Functional event-emitter library for javascript. Each time you yall a function on a current mockingbird, a new mockingbird is returned to the caller. This allows you to chain multiple emits and provides composability of event emitters.

```javascript
import mockingbird fromm 'mockingbird'

const emitter = 
  mockingbird()
    .on("hello", () => console.log("hello there")
    .on("goodbye", (data) => console.log(`Goodbye ${data})
    
emitter
  .emit("hello")
  .emit("goodbye", "Jim")
```

## API

### `on(event, handler)`
Create a new event emitter with the given event and its associated handler
### `close(event)`
Creates a new event emitter without the event in its listeners
### `off()`
Creates a new event emitter without any listeners
### `emit(event, data)`
Emit an event to the subscribers to the current emitter and returns a new event emitter with the same listeners
### `listeners()`
Retrieves an array of listeners from the current event emitter
