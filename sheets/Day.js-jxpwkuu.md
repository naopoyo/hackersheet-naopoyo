---
name: "Day.js"
slug: "jxpwkuu"
---

# Day.js

moment.jsの代わりに日付処理にDay.jsを使う。

## 公式

- [Day.js · 2kB JavaScript date utility library](https://day.js.org/)
- [iamkun/dayjs: ⏰ Day.js 2KB immutable date-time library alternative to Moment.js with the same modern API](https://github.com/iamkun/dayjs)
## インストール

```
npm install dayjs --save
```

## 使い方

```typescript
import dayjs from 'dayjs';

dayjs().format('YYYY/MM/DD')
```