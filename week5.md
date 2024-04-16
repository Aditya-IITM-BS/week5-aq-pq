# Week 5 Questions

### Q1. Which of the following statement(s) is/are true?

A non async function cannot use fetch API in its body.

An async function always returns a promise.

Fetch API can be used to make HTTP DELETE requests.

Fetch API does not allow modifications in the request headers.

### Q2. Which of the following statement(s) is/are true regarding Vue lifecycle hooks? (MSQ)

The lifecycle hooks are triggered implicitly, depending on the state of the component.

The created() hook is invoked when the reactive data properties have been set up.

The lifecycle hooks have to be triggered by the developer explicitly.

The lifecycle hooks cannot be async.

### Q.3 server is down, what will be shown on the console?

```js
new Vue({
  el: "#app",
  data() {
    return {
      time: [],
    };
  },
  created() {
    fetch("http://thisserverisdown.com")
      .then((res) => res.json())
      .then((data) => {
        this.time = data;
        console.log(this.time);
      })
      .catch((error) => {
        console.log("failed to fetch");
      });
  },
});
```

Failed to fetch

Reference error

Server Down

None of the above

### Q4. Predict the output

```js
let start = 5;
function check() {
  return new Promise((resolve, reject) => {
    let a1 = setInterval(() => {
      start++;
      if (start == 7) {
        console.log("reached");
        clearInterval(a1);
        resolve("pass");
        reject("fail");
      } else {
        console.log("yet to reach");
      }
    }, 500);
  });
}

check()
  .then((pass) => console.log(pass))
  .catch((fail) => console.log(fail));
```

1. Yet to Reach

   Reached

   Pass

2. Yet to Reach

   Reached

   Pass

   Fail

3. Yet to Reach

   Reached

   Fail

4. Yet to Reach

   Yet to Reach

   Reached

   Pass

   Fail

### Q5

```js
let x = 2,
  n = 3,
  k = 4;
const p1 = new Promise((resolve, reject) => {
  if (k < n) {
    resolve(x);
  } else {
    reject("bad promise");
  }
});

const p2 = p1.then((x) => {
  return x * x;
});

p2.then((x) => {
  console.log(x);
}).catch((err) => {
  console.log(err);
});
```

what will be logged on console

2

4

8

bad promise
