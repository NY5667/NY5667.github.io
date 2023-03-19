---
layout: post
title:  "How To Format A Date As YYYY-MM-DD Hh:mm:ss In JavaScript"
date:   2023-03-19 10:19:06 +0800
categories: NY5667 update
---
```javascript
var dateNow = new Date();
var beginTime =
              [dateNow.getFullYear(),
               dateNow.getMonth()+1,
               dateNow.getDate()].join('-')+' '+
              [dateNow.getHours(),
               dateNow.getMinutes(),
               dateNow.getSeconds()].join(':');
```

```java
@RequestParam("endTime") @DateTimeFormat(pattern="yyyy-MM-dd HH:mm:ss") Date endTime
```
[https://learnshareit.com/how-to-format-a-date-as-yyyy-mm-dd/][format-date]

[format-date]: https://learnshareit.com/how-to-format-a-date-as-yyyy-mm-dd/