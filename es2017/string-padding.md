# String padding

* `padStart`: number만큼 string내 나머지를 공백으로 채움 \(시작점\)
* `padEnd`: number만큼 string내 나머지를 공백으로 채움 \(종료점으로\)

```javascript
str.padStart(targetLength [, padString])
str.padEnd(targetLength [, padString])
```

* default는 공백임 \(다른 string\)으로 채우기 가능

```javascript
'es8'.padStart(2);          // 'es8'
'es8'.padStart(5);          // '  es8'
'es8'.padStart(6, 'woof');  // 'wooes8'
'es8'.padStart(14, 'wow');  // 'wowwowwowwoes8'
'es8'.padStart(7, '0');     // '0000es8'
'es8'.padEnd(2);          // 'es8'
'es8'.padEnd(5);          // 'es8  '
'es8'.padEnd(6, 'woof');  // 'es8woo'
'es8'.padEnd(14, 'wow');  // 'es8wowwowwowwo'
'es8'.padEnd(7, '6');     // 'es86666'
```

| Chrome | Firefox | Edge | Opera | Safari |
| :--- | :--- | :--- | :--- | :--- |
| 57 | 48 | 15 | 44 | 10 |

