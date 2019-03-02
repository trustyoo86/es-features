# 2\) Named Capture Groups

* 정규식 패턴에서 캡쳐 그룹을 사용하여 참조함

```javascript
const re = /(\d{4})-(\d{2})-(\d{2})/;
const match= re.exec('2019-01-10');

console.log(match[0]);    // → 2019-01-10
console.log(match[1]);    // → 2019
console.log(match[2]);    // → 01
console.log(match[3]);    // → 10
```

* 어떤것이 year, month, day인지 확인 불가능함.
* ES2018에서는 `$<name>...` 구문을 사용하여 캡쳐 그룹의 네이밍을 지정 가능함.

```javascript
const re = /(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})/;
const match = re.exec('2019-01-10');

console.log(match.groups);          // → {year: "2019", month: "01", day: "10"}
console.log(match.groups.year);     // → 2019
console.log(match.groups.month);    // → 01
console.log(match.groups.day);      // → 10
```

