아래 코드의 실행 결과와 왜 그렇게 동작하는지 설명해주세요.
```js
const Person = name => {
  this.name = name;
};

console.log(Person.prototype);
```
- undefined, 생성자 함수로서 호출할 수 없는 함수, 즉 non-constructor는 프로토타입이 생성되지 않는다.

아래 코드의 실행 결과와 왜 그렇게 동작하는지 설명해주세요.
```js
const Person = (function () {
  function Person(name) {
    this.name = name;
  }
  Person.prototype.sayHello = function () {
    console.log(`Hi! My name is ${this.name}.`);
  };
  return Person;
})();
const me = new Person("Lee");
me.sayHello = function () {
    console.log(`Hey! My name is ${this.name}.`);
};

me.sayHello();
delete me.sayHello;
me.sayHello();
delete me.sayHello;
me.sayHello();
```
- Hey! My name is Lee.
- Hi! My name is Lee.
- Hi! My name is Lee.
- 인스턴스 메서드 sayHello가 동명의 프로토타입 메서드를 오버라이딩(overriding)했고 프로토타입 메서드는 가려진다. 이와 같이 상속 관계에 의해 프로퍼티가 가려지는 현상을 프로퍼티 섀도잉(property shadowing)이라고 한다.
- 또한 하위 객체에 의해 프로토타입의 프로퍼티를 변경하거나 삭제할 수는 없으므로, 두번째 `delete me.sayHello` 구문의 실행은 아무 의미를 가지지 않는다. 프로토타입 프로퍼티를 변경 또는 삭제하려면 프로토타입에 직접 접근해야 한다. (ex. `delete Person.prototype.sayHello`)

instanceof 연산자에 대해서 설명해주세요.
- instanceof 연산자는 이항 연산자로, 좌변에 객체를 가리키는 식별자, 우변에 생성자 함수를 가리키는 식별자를 피연산자로 받는다. 우변의 생성자 함수의 prototype에 바인딩 된 객체가 좌변의 객체의 프로토타입 체인상에 존재하면 true로, 아니면 false로 평가된다.