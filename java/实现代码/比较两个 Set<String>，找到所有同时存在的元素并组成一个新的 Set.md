#### 实现目标：比较两个 `Set<String>`，找到所有同时存在的元素并组成一个新的 `Set`

以下是实现代码：

```java
import java.util.HashSet;
import java.util.Set;

public class Main {
    public static void main(String[] args) {
        // 创建两个 Set<String> 并赋值
        Set<String> set1 = new HashSet<>(Set.of("Apple", "Banana", "Orange"));
        Set<String> set2 = new HashSet<>(Set.of("Banana", "Grape", "Orange"));

        // 找到两个 Set 中共同存在的元素
        Set<String> commonElements = new HashSet<>(set1); // 复制 set1
        commonElements.retainAll(set2); // 保留 set2 中也存在的元素

        // 输出结果
        System.out.println("Common Elements: " + commonElements);
    }
}
```

---

#### 代码说明

1. **创建 `Set` 并赋值**：
   - 使用 `Set.of()` 方法创建两个 `Set<String>` 对象 `set1` 和 `set2`。
   - `Set.of()` 是 Java 9 引入的工厂方法，用于创建不可变集合。

2. **找到共同元素**：
   - 使用 `new HashSet<>(set1)` 复制 `set1` 到 `commonElements`。
   - 调用 `retainAll(set2)` 方法，保留 `set2` 中也存在的元素。

3. **输出结果**：
   - 使用 `System.out.println()` 输出共同元素。

---

#### 输出结果

运行代码后，输出如下：

```
Common Elements: [Banana, Orange]
```

---

#### 注意事项

1. **简洁性**：代码通过 `retainAll()` 方法实现了简洁的共同元素查找。
2. **性能**：`HashSet` 的查找和操作时间复杂度为 O(1)，适合处理大量数据。
3. **不可变性**：`Set.of()` 创建的集合是不可变的，如果需要修改，可以将其复制到 `HashSet` 中。

---

通过上述代码，你可以快速找到两个 `Set<String>` 中的共同元素并组成一个新的 `Set`。