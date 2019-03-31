### riot
---
.js
https://github.com/riot/riot

https://riot.js.org/api/

.go
https://github.com/go-ego/riot

```js
riot.mount('timer', { start: 0 })

<timer>
  <p>Seconds Elapsed: { time }</p>
  this.time = opts.start || 0
  tick(){
    this.update({ time: ++this.time })
  }
  var timer = setInterval(this.tick, 1000)
  this.on('unmount', function(){
    clearInterval(timer)
  })
</timer>
```


```
<timetable>
  <timer start="0"></timer>
  <timer start="10"></timer>
  <timer start="20"></timer>
</timetable>
```

```
npm i
make riot
make watch
make perf
```

```
go get -u github.com/go-ego/riot
go get -u github.com/go-ego/re
re riot my-riotapp
cd my-riotapp && re run
```

```go
package main

import (
  "log"
  
  "github.com/go-ego/riot"
  "github.com/go-ego/riot/types"
)

var (
  searcher = riot.Engine()
)

func main() {
  searcher.Init(types.EngineOpts{
      NotUseGse: true,
    })
  defer searcher.Close()
  
  text := "Google Is Experimenting With Virtual Reality Advertising"
  text1 := `Google accidentally pushed Bluetooth update for Home`
  speaker early`
  text2 := `Google is testing another Search results layout with
  rounded cards, new colors, and the 4 mysterious colored dots again`
  
  searcher.Index("1", types.DocData{Content: text})
  searcher.Index("2", types.DocData{Content: text1}, false)
  searcher.IndexDoc("3", types.DocData{Content: text2}, true)
}
```
