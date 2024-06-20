---
title: "通过Python脚本生成站点的"
weight: 3
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

`Python`脚本

```python
from lxml import etree
import requests, os

if __name__ == "__main__":

    file_path = r"e:\urls.txt"
    try:
        os.remove(file_path)
    except OSError:
        pass

    with open(file_path, 'a') as url_file:
        xml_dict = {}

        r = requests.get("https://lucumt.info/sitemap.xml")
        root = etree.fromstring(r.content)
        count = 0
        for sitemap in root:
            data = sitemap.getchildren()[0].text
            if 'tags' in data or 'categories' in data:
                continue
            count = count + 1
            url_file.write(data + '\n')
        print(f"Url files write success,total count {count}")
```

提交百度收录

```bash
curl -H 'Content-Type:text/plain' --data-binary @urls.txt "http://data.zz.baidu.com/urls?site=https://lucumt.info&token=xxx"
```

