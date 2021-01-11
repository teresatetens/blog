---
layout: post
title: Lodash Codecademy - part i

---

#### Lodash a Codecademy Project : JAVASCRIPT SYNTAX, PART II

Followed on the syllabus of codecademy, today's challenge was to build lodash method using vanilla javascript. I don't like to create an object for all the methods, so I just made functional approach. 

After all, it is a revisit on JavaScript and I had fun:  7 methods in 5 hours.

codesandbox with test data and answers: [https://codesandbox.io/s/lodashcodecademy20210111-0eusz?file=/src/index.js:0-4268]( https://codesandbox.io/s/lodashcodecademy20210111-0eusz?file=/src/index.js:0-4268)

- *clamp()*, *inRange()*, *words()*,*pad()*,*has()* ,*invert()*,*findKey()*

```
const clamp = (number, lower, upper) => {
  if (Math.max(number, lower, upper) === number) {
​    return upper;
  } else if (Math.min(number, lower, upper) === number) {
​    return lower;
  } else {
​    return number;
  }
};
```

```
const inRange = (num, start, end) => {
  if (!end) {
​    end = start;
​    start = 0;
  }

  if (num < Math.min(start, end) || num >= Math.max(start, end)) {
​    return false;
  } else {
​    return true;
  }
};
```

```
const words = (str) => {
  return str.split(" ");
};
```

```
const pad = (str, num) => {
  let spaceLength = num - str.length;
  if (spaceLength > 0) {
​    let frontPad = "";
​    let frontSpace = Math.floor(spaceLength / 2);
​    let leftSpace = spaceLength - frontSpace;
​    for (let i = 0; i < frontSpace; i++) {
​      frontPad = frontPad.concat("+");
​    }
​    let pad = frontPad.concat(str);
​    for (let i = 0; i < leftSpace; i++) {
​      pad = pad.concat("*");
​    }
​    return pad;
  } else {
​    return str;
  }
};
```

```
const has = (obj, key) => {
  let keyArr = Object.keys(obj);
  if (keyArr.includes(key)) {
​    return true;
  } else {
​    return false;
  }
};
```

```
const invert = (obj) => {
  const newObj = Object.fromEntries(
    Object.entries(obj).map(([key, value]) => [value, key])
  );
  return newObj;
};
```

```
const findKey = (obj, predicate) => {
  for (let key in obj) {
​    if (predicate(obj[key])) {
​      return key;
​    }
  }
  return undefined;
};

const startsWithV = (string) => string.startsWith("v");
```

