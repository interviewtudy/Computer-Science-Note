# 질문

## 1️⃣ 인터페이스와 추상클래스의 공통점과 차이점

### 공통점

- 상속/구현 하는 클래스가 추상 메서드를 구현하도록 강제함
- 직접 인스턴스를 생성할 수 없음

### 차이점

<table>
  <thead>
    <tr>
      <th>항목</th>
      <th>인터페이스</th>
      <th>추상클래스</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>목적</td>
      <td>어떤 기능을 제공할지 행동을 정의</td>
      <td>공통된 속성과 행동을 제공함</td>
    </tr>
    <tr>
      <td>속성</td>
      <td>가질 수 없음</td>
      <td>가질 수 있음</td>
    </tr>
    <tr>
      <td>메서드 구현</td>
      <td>구현 불가(모든 메서드가 추상 메서드)</td>
      <td>구현 가능(일반 메서드 + 추상메서드 혼용 가능)</td>
    </tr>
    <tr>
      <td>다중 상속 여부</td>
      <td>가능</td>
      <td>불가능</td>
    </tr>
    <tr>
      <td>생성자</td>
      <td>가질 수 없음</td>
      <td>가질 수 있음</td>
    </tr>
  </tbody>
</table>

## 2️⃣ 추상 팩토리 패턴 vs 팩토리 메서드 패턴

### 공통점

- 객체 생성 과정을 추상화한 인터페이스를 제공
- 객체 생성을 캡슐화 -> 느슨한 결합 상태

### 차이점

```java
/* 추상 팩토리 패턴 */
interface MenuFactory {
  MainMenu createMainMenu();
  SubMenu createSubMenu();
}

class LunchMenuFactory implements MenuFactory {
  public MainMenu createMainMenu() {
    return new MainMenuA();
  }

  public SubMenu createSubMenu() {
    return new SubMenuA();
  }
}

class DinnerMenuFactory implements MenuFactory {
  public MainMenu createMainMenu() {
    return new MainMenuB();
  }

  public SubMenu createSubMenu() {
    return new SubMenuB();
  }
}

/* 추상 메서드 패턴 */
abstract class Menu {
  public abstract String getName();
}

class MenuA extends Menu {
  private String name;

  public MenuA(String name) {
    thsi.name = name;
  }

  public String getName() {
    return this.name;
  }
}

class MenuB extends Menu {
  private String name;

  public MenuB(String name) {
    thsi.name = name;
  }

  public String getName() {
    return this.name;
  }
}

class MenuFactory {
  public static Menu getMenu(String type) {
    if ("MenuA".equalsIgnoreCase(type)) return new MenuA(type);
    else if ("MenuB".equalsIgnoreCase(type)) return new MenuB(type);
  }
}

public class HelloWorld {
  public static void main(String[] args) {
    Menu menuA = MenuFactory.getName("MenuA");
    Menu menuB = MenuFactory.getName("MenuB");
  }
}

```

- 추상 팩토리 패턴을 보면 메인 메뉴 객체와 서브 메뉴 객체라는 관련 있는 두 객체의 생성 과정 집합을 MenuFactory 에 추상화 했음
- 추상 메서드 패턴을 보면 메뉴라는 한 추상 객체에 대한 하위 클래스들의 생성 과정을 MenuFactory 에 분리했음. 만약 이렇게 분리하지 않았다면 main 함수 내에서 직접 객체를 생성하고 사용했어야 했겠지만, 분리를 완료 했기 때문에 MenuFactory 객체를 생성하고 main 에서는 그를 가져다 쓰기만 할 수 있음

# 추가 정리

## 디자인 패턴의 분류

생성 패턴, 구조 패턴, 행위 패턴으로 분류할 수 있음

### 생성 패턴(Creational Pattern)

- 클래스 정의와 객체 생성 방식을 구조화, 캡슐화한 방법을 제시함
- 객체의 생성과 참조 과정을 추상화하여 시스템 개발 시 부담을 덜어줌
- ex. 싱글톤 패턴, 팩토리 패턴

### 구조 패턴(Structural Pattern)

- 클래스나 객체를 조합해 더 큰 구조를 만드는 패턴
- 복잡한 형태의 구조를 갖는 시스템을 개발하기 쉽게 만들어줌
- ex. 프록시 패턴

### 행위 패턴(Behavioral Pattern)

- 반복적으로 사용되는 객체 간의 상호 작용을 패턴화 함
- 클래스나 객체들이 상호작용하는 방법과 책임을 분산함
- ex. 옵저버 패턴, 전략 패턴, 이터레이터 패턴

## 함수형 프로그래밍의 특징

### 커링(Currying)

- 커링이란 다중 인수를 갖는 함수를 단일 인수를 갖는 함수들의 함수열로 바꾸는 것을 의미함

  ```javascript
  /* 커링 미적용 시 */
  function add(a, b) {
    return a + b;
  }

  function addTwo(a) {
    return add(a, 2);
  }

  function addThree(a) {
    return add(a, 3);
  }

  /* 커링 적용 시 */
  function addX(x) {
    return function (a) {
      return add(a, x);
    };
  }

  const addTwo = addX(2);
  const addThree = addX(3);

  /* 커링 적용 & 화살표 함수 */
  const addX = (x) => (a) => add(a, x);
  ```

- 함수의 재활용과 더 가벼운 함수 제작을 위해 사용함

### 불변성

어떤 변수에 한번 값을 할당하고 나면 어떤 방법으로도 해당 변수의 값을 바꿀 수 없게 함

## Call By Value & Call By Reference & Call By Assignment

함수의 인자 전달 방식으로, 함수에서 인자의 값을 어떻게 호출하는지에 따라 나뉨

- Call By Value: 변수의 복사값을 전달하는 방식
- Call By Reference: 변수의 주소값을 전달하는 방식
- Call By Assignment: 인자의 자료형에 따라 Call By Value(Immutable Object의 경우), Call By Reference(Mutable Object의 경우) 가 달라짐.<br/>파이썬에서 사용
