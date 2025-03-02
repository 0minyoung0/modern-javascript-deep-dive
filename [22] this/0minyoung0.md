# [22] this

### 1. this는 무엇인가요?

- this는 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수(self-referencing variable)다. this를 통해 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있다.

### 2. this 바인딩은 무엇인가요?

- 바인딩은 식별자와 값을 연결하는 과정을 의미한다. this 바인딩은 this(키워드로 분류되지만 식별자 역할을 한다)와 this가 가리킬 객체를 바인딩하는 것이다.

### 3. strict mode가 아닌 경우 일반 함수로 호출된 함수의 this에는 무엇이 바인딩되나요?

- 전역 객체

### 4. 메서드 내부의 this에는 무엇이 바인딩되나요?

- 메서드를 호출한 객체

### 5. 생성자 함수 호출 시 this에는 무엇이 바인딩되나요?

- 생성자 함수가 (미래에) 생성할 인스턴스

### 6. `Function.prototype.apply`, `Function.prototype.call`, `Function.prototype.bind` 메서드에 의한 간접 호출에 의해서는 this에 무엇이 바인딩되나요?

- `Function.prototype.apply/call/bind`메서드에 첫 번째 인수로 전달한 객체
