### riot
---
.js
https://github.com/riot/riot

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

