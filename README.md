# Algorithms Notes
Мои заметки по алгоритмам и структурам данных.


## Шаблон заметки
### Two Sum 
**Ссылка:** https://leetcode.com/problems/xxx/

**Сложность:** Easy/Medium/Hard

**Тема:** Arrays, Hash Map, etc

### Идея
Идём по массиву, для каждого элемента проверяем, есть ли в хеш-таблице `target - nums\[i]`. Если есть — возвращаем индексы. Если нет — кладём текущий элемент в таблицу.

### Сложность
- Время: O(n)
- Память: O(n)

### Что было сложно
Сначала пыталась решить двумя циклами — O(n²). Не догадалась использовать хеш-таблицу для поиска пары за O(1).

### Код

```java
public int[] twoSum(int[] nums, int target) {
    Map<Integer, Integer> map = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
        int complement = target - nums[i];
        if (map.containsKey(complement)) {
            return new int[] { map.get(complement), i };
        }
        map.put(nums[i], i);
    }
    throw new IllegalArgumentException("No solution");
}
```

