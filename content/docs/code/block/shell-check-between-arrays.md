---
title: "Shell数组中模糊检测"
weight: 4
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

检测数组a中的元素是否模糊包含数组b中的一个或多个元素

```bash
#!/bin/bash

# 数组a和数组b的定义
a=("tainan" "taipei" "taichung" "keelung" "taoyuan" "changhua" "nantou" "kinmen")
b=("tai" "nan")


for element_a in "${a[@]}"; do
    contains=false
    for pattern in "${b[@]}"; do
        if [[ $element_a =~ $pattern ]]; then
            contains=true
            break
        fi
    done
    if [  "$contains" = true ] ; then
      echo "----------$element_a符合要求---------------"
    else
      echo "**********$element_a不符合要求************"
    fi
done
```

