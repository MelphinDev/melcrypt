# Melcrypt

##  Usage

#### Node.js

```js

const melcrypt = require('melcrypt');

```

#### Bowser

```js
import { melcrypt } from './dist/melcrypt.mjs';

```

or

```html

<script src="./dist/melcrypt.min.js"></script>

```

#### Example

```js

let encode = 'hex', // 'base64'
data = 'test text';

let obj = {
  key: melcrypt.generateKey(encode),
  key2x: [ melcrypt.generateKey(encode), melcrypt.generateKey(encode) ],
  key3x: [ melcrypt.generateKey(encode), melcrypt.generateKey(encode), melcrypt.generateKey(encode)],
  algo: 'TWOFISH',
  algo2x: ['TWOFISH', 'SERPENT'],
  algo3x: ['TWOFISH', 'SERPENT', 'AES']
}

obj.ctext = melcrypt.encrypt(data, obj.key, obj.algo, encode);
obj.ptext = melcrypt.decrypt(obj.ctext, obj.key, obj.algo, encode)

obj.ctext2x = melcrypt.encrypt2x(data, obj.key2x, obj.algo2x, encode);
obj.ptext2x = melcrypt.decrypt2x(obj.ctext2x, obj.key2x, obj.algo2x, encode);

obj.ctext3x = melcrypt.encrypt3x(data, obj.key3x, obj.algo3x, encode);
obj.ptext3x = melcrypt.decrypt3x(obj.ctext3x, obj.key3x, obj.algo3x, encode);


console.log(obj)
```
