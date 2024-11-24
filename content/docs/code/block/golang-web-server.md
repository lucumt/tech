---
title: "利用Go生成简易的Web Server"
weight: 6
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

采用`Golang`生成Web Server无需额外处理相关的静态文件等引用，会减少代码量和维护工作量

```go
package main

import (
	"encoding/json"
	"io/ioutil"
	"log"
	"net/http"
	"os"
	"strconv"
)

type ConfigData struct {
	Info string `json:"info"`
	File string `json:"file"`
	Port int    `json:"port"`
}

func parseConfigFile() ConfigData {
	jsonFile, err := os.Open("config.json")
	if err != nil {
		log.Println(err)
	}
	log.Println("Successfully Opened config.json")

	defer jsonFile.Close()

	byteValue, _ := ioutil.ReadAll(jsonFile)

	var config ConfigData
	err = json.Unmarshal(byteValue, &config)
	if err != nil {
		log.Fatal(err)
	}
	return config
}

func main() {
	var config = parseConfigFile()
	log.Println("port: " + strconv.Itoa(config.Port))
	log.Println("file: " + config.File)
	log.Println(config.Info)
	log.Println("可通过 http://127.0.0.1:" + strconv.Itoa(config.Port) + " 访问此系统")

	http.Handle("/", http.FileServer(http.Dir(config.File)))
	http.ListenAndServe(":"+strconv.Itoa(config.Port), nil)
}
```



