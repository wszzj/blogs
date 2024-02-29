# Promise

```
class Promise1 {
  #status = 'pending'
  constructor(fn){
    this.q = []
    const resolve = (data)=>{
      this.#status = 'fulfilled'
      const f1f2 = this.q.shift()
      if(!f1f2 || !f1f2[0]) return
      const x = f1f2[0].call(undefined, data)
      if(x instanceof Promise1) {
        x.then((data)=>{
          resolve(data)
        }, (reason)=>{
          reject(reason)
        })
      }else {
        resolve(x)
      }
    }
    const reject = (reason)=>{
      this.#status = 'rejected'
      const f1f2 = this.q.shift()
      if(!f1f2 || !f1f2[1]) return
      const x = f1f2[1].call(undefined, reason)
      if(x instanceof Promise1){
        x.then((data)=>{
          resolve(data)
        }, (reason)=>{
          reject(reason)
        })
      }else{
        resolve(x)
      }
    }
    fn.call(undefined, resolve, reject)
  }
  then(f1, f2){
    this.q.push([f1, f2])
  }
}

const p = new Promise1(function(resolve, reject){
  setTimeout(function(){
    reject('出错')
  },3000)
})

p.then( (data)=>{console.log(data)}, (r)=>{console.error(r)} )
```

# Promise.all

```
Promise.myAll = function(list){
  const results = []
  let count = 0
  return new Promise((resolve,reject) =>{
    list.map((item, index)=> {
      item.then(result=>{
          results[index] = result
          count += 1
          if (count >= list.length) { resolve(results)}
      }, reason => reject(reason) )
    })
  })
}
```