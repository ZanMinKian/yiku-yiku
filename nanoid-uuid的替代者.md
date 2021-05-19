# nanoid-uuid替代者

## 安装

```bash
npm i nanoid
```

## 使用

```typescript
import { nanoid } from 'nanoid'
model.id = nanoid() //=> "V1StGXR8_Z5jdHi6B-myT"
```

## Why

### nanoid

- **Small.** 108 bytes (minified and gzipped). No dependencies. [Size Limit](https://github.com/ai/size-limit) controls the size.
- **Fast.** It is 60% faster than UUID.
- **Safe.** It uses cryptographically strong random APIs. Can be used in clusters.
- **Compact.** It uses a larger alphabet than UUID (`A-Za-z0-9_-`). So ID size was reduced from 36 to 21 symbols.
- **Portable.** Nano ID was ported to [14 programming languages](https://www.npmjs.com/package/nanoid#other-programming-languages).

### uuid

uuid使用ts时不够友好。

安装`"@types/uuid": "^8.3.0"`，tsconfig.json开启`"esModuleInterop": true`和`"allowSyntheticDefaultImports": true`，使用uuid时，必须如下：

```typescript
import { v4 as uuidv4 } from 'uuid'
uuidv4()
// 或
import * as uuid from 'uuid'
uuid.v4()
```

不能如下：

```typescript
import uuid from 'uuid'
uuid.v4() // 此处编译不报错，但是运行的时候会报错
```

