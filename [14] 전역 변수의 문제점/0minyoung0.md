다음 코드의 실행 결과가 무엇일까요?
```js
var x = 'global';
function foo() {
    console.log(x);
    var x = 'local';
}

foo();
console.log(x);
```
- undefined, global 출력

전역 변수의 문제점에는 어떤 것이 있는지 설명해주세요.
- 긴 생명 주기(메모리 리소스도 오랜 기간 소비), 스코프 체인 상에서 종점에 존재(변수 중 전역 변수의 검색 속도가 가장 느림), 네임스페이스 오염(파일이 분리되어 있다해도 하나의 전역 스코프를 공유한다기 때문에, 다른 파일 내에서 동일한 이름으로 명명된 전역 변수나 적역 함수가 같은 스코프 내에 존재하는 경우)

다음 코드의 실행 결과가 무엇일까요?
```js
var Counter = (function () {
    var num = 0;

    return {
        increase() {
            return ++num;
        },
        decrease() {
            return --num;
        }
    };
}());

console.log(Counter.num);
console.log(Counter.increase());
console.log(Counter.increase());
console.log(Counter.decrease());
console.log(Counter.decrease());
```
- undefined, 1, 2, 1, 0