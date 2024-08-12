---
title: "Java中利用Lambda进行过滤"
weight: 5
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# 复杂的过滤

```java
import com.google.common.collect.Lists;
import lombok.AllArgsConstructor;
import lombok.Data;
import org.apache.commons.lang3.StringUtils;

import java.util.List;
import java.util.stream.Collectors;

public class FilterTest {

    public static void testData() {
        List<Record> recordsA = Lists.newArrayList(
                new Record("A", "a1"),
                new Record("A", "a2"),
                new Record("A", "a4"),
                new Record("A", "a5"),
                new Record("B", "b1"),
                new Record("B", "b2"),
                new Record("B", "b7"),
                new Record("D", "b7")
        );
        List<Record> recordsB = Lists.newArrayList(
                new Record("A", "a1"),
                new Record("A", "a2"),
                new Record("A", "a3"),
                new Record("B", "b1"),
                new Record("B", "b2"),
                new Record("B", "b3"),
                new Record("B", "a1"),
                new Record("C", "c1"),
                new Record("C", "c2"),
                new Record("C", "b1")
        );

        // 查找出新增的
        List<Record> addRecordsA = recordsB.stream().filter(n -> recordsA.stream().noneMatch(o -> StringUtils.equals(o.getCate(), n.getCate()))).collect(Collectors.toList());
        List<Record> addRecordsB = recordsB.stream().filter(n -> recordsA.stream().filter(o -> StringUtils.equals(o.getCate(), n.getCate())).noneMatch(o -> StringUtils.equals(o.getProd(), n.getProd()))).collect(Collectors.toList());
        List<Record> addRecordsC = recordsB.stream().filter(n -> recordsA.stream().noneMatch(o -> StringUtils.equals(o.getProd(), n.getProd()))).collect(Collectors.toList());
        System.out.println(addRecordsA);
        System.out.println(addRecordsB); // 只有这个符合要求
        System.out.println(addRecordsC);

        // 查找删除的
        List<Record> deleteRecordsB = recordsA.stream().filter(n -> recordsB.stream().filter(o -> StringUtils.equals(o.getCate(), n.getCate())).noneMatch(o -> StringUtils.equals(o.getProd(), n.getProd()))).collect(Collectors.toList());
        System.out.println(deleteRecordsB);
    }

    @Data
    @AllArgsConstructor
    public static class Record {
        private String cate;
        private String prod;
    }
}
```



