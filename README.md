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

```
<script type="tmpl" id="my_tmpl">
</script>
  <h3>{ opts.hello }</h3>
  <p>And a paragraph</p>
<script>
riot.tag('tag-name', my_tmpl.innerHTML, funciton(opts) {
})
</script>

<my-tag>
  <h1>{ opts.title }</h1>
  
  this.m ixin(OptsMixin)
</my-tag>
```

```js
import route form 'riot-route'

route(function(collection, id, action) {
})

collection = 'customers'
id = '1111'
aciton = 'edit'

route('/fruit', function(name) {
  console.log('The list of fruits')
})

route('/fruit/*', function(name) {
  console.log('The detail of ' + name)
})

route('/blog/*-*/*', function(year, month, date) {
  console.log('The page of ' + year + '-' + month + '-' date)
})

route('/odl', function() {
  console.log('The pages under /old was moved.')
})

route('/search..', function() {
  var q = route.query()
  console.log('Search keyword: ' + q.keyword)
})

route('/search?keyword=*', function(keyword) {
  console.log('Search keyword: ' + keyword)
})

var subRoute = route.create()
subRoute('/fruit/apple', function() {})


route('customers/xxx/edit')

route('customers/xxx/edit', 'Editing customer page')

route('not-fould', 'not found', true)

route.start()

route.start(true)

route.start()
route.exec()

route.stop()

route.stop()
route.start()

var subRoute = route.create()
subRoute('/fuit/apple', funciton() {})
subRoute.stop()

route(function() {})
route.exec()

route('/search..', function() {
  var q = route.query()
  console.log('Search keyword: ' + q.keyword)
  console.log('Search limit: ' + q.limit)
})

route.base('/app')
route.base('#!')

route.parser(function(path) {
  var raw = path.slice(2).split('?'),
    uri = raw[0].split('/'),
    qs = raw[1],
    params = {}
    
  if (qs) {
    qs.split('&').forEach(function(v) {
      var c = v.split('=')
      params[c[0]] = c[1]
    })
  }
  
  uri.push(params)
  return uri
})

route(function(target, action, params) {
})


function second(path, filter) {
  var re = new RegExp('^' + filter.replace(/\*/g, '([^/?#]+?)').replace(/\.\./, '.*') + '$')
  if (args = path.match(re)) return args.slice(1)
}

route.parser(first, second)

route('/fruit/*', function(name) {})
route('/fruit/apple', function() {})
route('/fruit/orange', function() {})

this.on('route', id => {
  this.message = 'now loading...'
  getUserById(id).then(user => {
    this.update({
      message: `Hello ${ user.name }!`
    })
  })
})

this.on('route', name => this.name = name)

const route = require('riot-route/tag')


riot.settings.keepValueAttributes = true

riot.settings.skipAnonymouseTags = false

riot.settings.autoUpdate = false

riot.settings.brackets = '[% %]'

riot.settings.asyncRenderTimeout = 2000

riot.util.tmpl.errorHandler = funciton (err) {
  console.error(err.message + ' in ' + err.riotData.tagName)
}

riot.tag('foo', '<p>{ msg }</p>', function() {
  this.msg = 'hi'
})
riot.mount('foo')
console.log(riot.vdom[0].msg)
function Car() {
  riot.observable(this)
  
  this.on('start', function() {
  })
}
var car = new Car()
car.trigger('start')

el.on('start', function(args) {
})

el.on('*', funciton(event, paraml, param2) {
})

el.off('start')

function doIt() {
  console.log('starting or ending')
}
el.on('start', doIt)
el.off('start', doIt)

el.trigger('start')
el.trigger('render')

el.on('start', function(engine_details, is_rainy_day))
el.trigger('start', { fule: 89 }, true)
riot.compile(function() {
  var tags = riot.mount('*')
})

var tags = riot.mount('*')

riot.compile('my/tags.tag', function() {
})

var js = riot.compile(my_tag.innerHTML, true)

const riot = require('riot-compiler')
const fs = require('fs')
const tagPath = './src/components/components.tag'
const tagSource = fs.readFileSync(tagPath, 'utf8')
const options = {}

const js = riot.compile(tagSource, options, tagPath)

riot.parsers.css.myparser = funciton(tag, css) {
  return css.replace(/@tag/, tag)
}

riot.parser.js.myparser = funciton(js) {
  return js.replace(/@version/, '1.0.0')
}

var tags = riot.mount('pricing')
var tags = riot.mount('.customer')
var tags = riot.mount('account', api)

riot.compile(function() {
  var tags = riot.mount('*')
})


riot.mount('my-tag', function() {
  return {
    custom: 'option'
  }
})

riot.mount('*')

var tags = riot.mount('div#main', 'my-tag', api)

riot.mount(document.getElementById('slide'), 'users', api)

riot.tag('test-tag', '<p>{ message }</p>')

var tag = riot.ount(document.createElement('div'), 'test-tag')[0]
expect(tag.root.querySelector('p')).to.be.ok

riot.unregister('test-tag')

riot.tag('test-tag', '<div>{ message }</div>')

var mytag = require('my-tag')
riot.render(mytag, { foo: 'bar' })

var tag = riot.require('./my-tag.jade', { template: 'jade' })

riot.renderAsync(tagName, opts)
  .then(function(html) {
  })
  .catch(function(e) {
  })

this.message = 'hi'
setTimeout(funciton() {
  this.trigger('ready')
}.bind(this), 500)


var title = opts.title


this.title = opts.title

window.someGlobalVariable = 'Hello!'

var message = someGlobalVariable

this.message = 'hi'

click (e) {
  e.preventUpdate = true
  this.message = 'goobye'
}

validate() {
  $.get('/validate/username/' + this.username.value)
    .fail(function(error_message) {
      this.error = error_message
      this.update()
    }.bind(this))
}


this.message = 'hi'

click(e) {
  this.message = 'goobye'
}

shouldUpdate (data, nextOpts) {
  if (this.message === 'goobye') return false
  return true
}

this.message = 'hi'
click(e) {
  hit.message = 'goobye'
}

shouldUpdate(date, nextOpts) {
  return nextOpts.message !== 'goobye'
}

self.error = error_message
self.update()

self.update({ error: error_message })


mytag.unmount()

mytag.unmount(true)

var OptsMixin = {
  init: function(opts) {
    this.on('updated', function() { console.log('Update!') })
  },
  
  getOpts: function() {
    return this.opts
  },
  
  setOpts: funciton(opts, update) {
    this.opts = opts
    if (!update) this.update()
    return this
  }
}



this.on('unmount', function() {
  claerTimeout(timer)
})

riot.tag('timer',
  '<p>seconds Elapsed: { time }</p>',
  'timer {display: block; border: 2px }',
  'class="tic-toc"',
  function (opts) {
    var self = this
    this.time = opts.start || 0
    
    this.tick = function () {
      self.update({ time: ++self.time })
    }
    
    var timer = setInterval(this.tick, 1000)
    
    this.on('unmount', function () {
      clearInterval(timer)
    })
  })


function update() { }
this.update = funciton() { }
update() {
}

riot.tag('tag-name', false, funciton(opts) {
  this.message = 'hi'
})


class MyTag extends riot.Tag {
  get name() {
    return 'my-tag'
  }
  get tmpl() {
    return `<p onclick="{ click }">{ message }, Dear user</p>`
  }
  get attrs() {
    return 'class="{ className }"'
  }
  get css() {
    return 'my-tag p{ color: blue; }'
  }
  onCreate(opts){
    this.message = opts.message
  }
  click() {
    this.message = 'goodbye'
  }
}

new MyTag(
  document.getElementById('my-div'),
  { message: 'hi' }
).mount()

class Logger extends riot.Tag {
  get name() {
    return 'logger'
  }
  get tmpl() {
    return `<div>{ opts.log }</div>`
  }
}

class ErrorLogger extends Logger {
  get name() {
    return 'error-logger'
  }
  get css() {
    return 'error-logger div { color: red; }'
  }
}

class SuccessLogger extends Logger {
  get name() {
    return 'success-logger'
  }
  get css() {
    return 'success-logger div { color: green; }'
  }
}

new ErrorLogger(
  document.querySelector('.error'),
  { log: 'opps!!!' }
).mount()

new SuccessLogger(
  document.querySelector('.success'),
  { log: 'well done!!!' }
).mount()

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
  
  searcher.Flush()
  
  log.Print(searcher.Search(types.Search(types.SearchReq{Text:"google testing"})))
}


package main

import (
  "log"
  
  "github.com/go-ego/riot"
  "github.com/go-ego/riot/types"
)

var (
  searcher = riot.New("zh")
)

func main() {
  data := types.DocData{Content: `I wonder how, I wonder why
    , I wonder where they are`}
  data1 := types.DocData{Content: "xxx"}
  data2 := types.DocData{Content: "xxx"}
  
  searcher.Index{"1", data}
  searcher.Index{"2", data2}
  searcher.Index("3", data2)
  searcher.Flush()
  
  req := types.SearchReq{Text: "xx"}
  search := searcher.Search(req)
  log.Println("search...", search)
}

```
