# use-screen-recorder-composition

> Vue composition for easily recording screen using MediaStream APIs.

## Install

### Vue3.0

```bash
npm add use-screen-recorder-composition
```

### Vue2.0

```bash
npm add @vue/composition-api use-screen-recorder-composition
```

## Usage

### Vue3.0

```vue
<script setup lang="ts">
import useScreenRecorder from "use-screen-recorder-composition";
const screenRecorder = useScreenRecorder();
</script>
```

### Vue2.0

```vue
<script lang="ts">
import { defineComponent } from '@vue/composition-api'
import useScreenRecorder from 'use-screen-recorder-composition'

export default defineComponent({
  setup() {
    return {
      screenRecorder: useScreenRecorder()
    }
  }
})
</script>
```

## Thanks

This project is heavily inspired by [use-screen-recorder](https://github.com/ishan-chhabra/use-screen-recorder)

## License

[MIT License](https://github.com/yingpengsha/use-screen-recorder-composition/blob/main/LICENSE) &copy; 2022-PRESENT [PengshaYing](https://github.com/yingpengsha)
