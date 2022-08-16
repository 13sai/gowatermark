# gowatermark

watermark powered with golang

```sh
go get github.com/13sai/gowatermark
```


```golang
package main

import (
	"fmt"
	"github.com/13sai/gowatermark"
)

func main() {
	wt := gowatermark.New()
	fileName := "go.jpeg"
	FontFile := "/System/Library/Fonts/STHeiti Medium.ttc" //字体路径
	str := gowatermark.FontInfo{24, "sai0556", gowatermark.TopLeft, 20, 20, 100, 100, 88, 255}
	err := wt.From(fileName).Font(FontFile).To("gowt.jpeg").AddWords(str).Do().Error()
	if err != nil {
		fmt.Println(err.Error())
	} else {
		fmt.Println("success")
	}
}
```