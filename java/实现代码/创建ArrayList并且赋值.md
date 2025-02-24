### 实现目标：创建 `ArrayList` 对象并同时赋值

以下是实现代码：

```java
import java.util.ArrayList;
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        // 创建 ArrayList 并同时赋值
        ArrayList<String> list = new ArrayList<>(Arrays.asList("Apple", "Banana", "Orange"));

        // 输出 ArrayList 内容
        System.out.println("ArrayList: " + list);
    }
}
```

---

### 代码说明

1. **`ArrayList` 创建**：
   - 使用 `new ArrayList<>()` 创建一个 `ArrayList` 对象。
   - 通过 `Arrays.asList()` 方法将初始值添加到 `ArrayList` 中。

2. **赋值**：
   - `Arrays.asList("Apple", "Banana", "Orange")` 返回一个包含初始值的列表。
   - 将该列表作为参数传递给 `ArrayList` 的构造函数，完成赋值。

3. **输出**：
   - 使用 `System.out.println()` 输出 `ArrayList` 的内容。

---

### 输出结果

运行代码后，输出如下：

```
ArrayList: [Apple, Banana, Orange]
```

---

### 注意事项

1. **简洁性**：代码通过 `Arrays.asList()` 实现了简洁的初始赋值。
2. **可扩展性**：可以根据需要修改初始值列表。
3. **泛型支持**：`ArrayList<String>` 指定了列表中的元素类型为 `String`，确保类型安全。

---

通过上述代码，你可以快速创建并初始化一个 `ArrayList` 对象。