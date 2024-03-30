# jest

* 테스트란 사용자가 실제로 사용하는 방식으로 소프트웨어를 테스트하는것
* jest, vitest: 테스트러너, 테스트를 실행하고 테스트의 통과, 실패 여부를 결정
* vitest가 jest보다 훨씬 빠르다
* TDD: 테스트 주도개발
  * 코드 작성 전에 테스트를 작성하고 테스트에 통과하도록 코드를 작성하는것 -> 레드-그린 테스트
  * 레드그린테스트: 코드 작성전 테스트에 실패하는 레드 테스트를 먼저 실행하고 코드 작성후 통과하는 테스트로 그린테스트를 확인하는것
* RTL(React Testing Library): 테스트를 위한 가상 dom을 생성하고 dom과 상호작용하기 위한 유틸리티도 제공
* 유닛테스트: 함수나 별개의 리액트 컴포넌트 코드의 한 유닛 혹은 단위를 테스트하는것, 다른 코드의 유닛과 상호작용하는것을 테스트하지 않는다
* 통합테스트: 여러 유닛이 함께 작동하는 방식을 테스트해서 유닛간의 상호작용을 테스트
* 기능테스트: 소프트웨어의 특정 기능을 테스트, 특정 코드 함수가 아닌 소프트웨어의 일반적인동작을의미
* e2e테스트: 실제 브라우저가 필요하고 애플리케이션이 연결된 서버가 필요

```
test('asdf', () ={
    render(<App />)

    const buttonElement = screen.
})
```
* screen 객체를 사용해서 render에서 생성된 시뮬레이션인 dom에 엑세스 할 수 있다
* 테스트 코드의 경우 코드가 반복되지 않거나 중복 코드를 피하는것이 그렇게 중요하지는 않다
* describe: 테스트를 그룹화하는 방법 
* 명세가 변경되면 기존 테스트는 업데이트 돼야한다
* 함수 (단위, 유닛) 테스트는 시능 테스트의 실패원인을 확인하고 싶을때도 유용하다
* fireEvnet를 사용해서 인터랙션 테스트 가능
* queryBy*: queryby로 시작하는 쿼리는 조건에 일치하는 앨리먼트 하나를 선택한다. 만약 존재하지 않아도 에러가 발생하지 않는다
* getBy*: getby로 시작하는 쿼리는 조건에 일치하는 dom 엘리먼트 하나를 선택한다. 만약 없으면 에러가 발생한다
* 서버연결은 거의 항상 비동기식이다. -> await, findBy를 사용해야한다
* 파일 안에 있는 여러 테스트를 분리하는법 ex) test.only  test.skip
* 네트워크 호출을 하는경우 데이터가 돌아올 때 이미 컴포넌트는 언마운트 되기 때문에 오류 발생
* 테스트에서 컴포넌트 렌더링 -> 네트워크 호출 트리거 -> unmount 메소드 실행해서 컴포넌트 언마운트 -> 언마운트 일어날때 네트워크 호출이 취소
* 명시적 언마운트가 필요한이유: testing librart에서 테스트 클린업의 일부로 컴포넌트를 언마운트 하면 명시적으로 컴포넌트를 언마운트해야한다.