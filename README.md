# 蒐集到好用的 React Hooks

搭配 `material-ui` 使用的 Hooks

---

- useForm
- useDebounce
- useDebouncedCallback 暫無註解
- useTimeout 暫無註解

---

## 使用方法

### useForm

快速綁定表單變數

```javascript
import { TextField }from '@material-ui/core';
import { useForm } from "./hooks";

const defaultFormState = {
  propA: "",
  propB: ""
};

const component = () => {
  const { form, handleChange, setForm } = useForm(defaultFormState);

  return (
    <TextField
      label="Label..."
      // 賦予 id、name 與 value 相同名稱即可
      id="propA"
      name="propA"
      value={form.propA}
      onChange={handleChange}
      ...restProps
    />
  );
};
```

### useDebounce

延遲防抖、增加執行效率

```javascript
import { useState } from "react";
import { useDebounce } from "./hooks";

// 延遲開合功能
const component = () => {
  const [opened, setOpened] = useState(false);
  const handleToggle = useDebounce(open => {
    setOpened(open);
  }, 150);

  return <div onMouseEnter={() => handleToggle(true)}>...children</div>;
};
```
