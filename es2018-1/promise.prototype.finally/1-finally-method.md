# 1\) finally\(\) method

* Promise의 resolve, reject 여부와 관계없이 해당 작업이 완료된 후 실행
* promise 작업이 완료된 후 정리작업 수행시 유용

```javascript
fetch('https://www.google.com')
  .then((response) => {
    console.log(response.status);
  })
  .catch((error) => { 
    console.log(error);
  })
  .finally(() => { 
    document.querySelector('#spinner').style.display = 'none';
  });
```

* 위의 코드에서는 ajax 처리 후 spinner 숨김처리
* `then()`, `catch()` 메서드에서는 resolve, reject, error에 대한 처리만 수행할 수 있도록 처리

