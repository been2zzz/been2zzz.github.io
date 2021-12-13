---
title: "Node.js 교과서 - 핵심 개념 이해하기"
excerpt_separator: "<!--more-->"
categories:
  - Node.js
tags:
  - Node.js
---

## 서버

네트워크를 통해 클라이언트에 정보나 서비스를 제공하는 컴퓨터 또는 프로그램

- 클라이언트의 요청에 대한 응답

---

## 자바스크립트 런타임

- 특정 언어로 만든 프로그램들을 실행할 수 있는 환경을 뜻함 (자바스크립트 실행기)
- Node.js는  Chrome V8 Javascript 엔진으로 빌드

![노드의 내부 구조](/assets/images/post/211213/Untitled.png)

노드의 내부 구조

- libuv 라이브러리
    - 노드의 특성인 이벤트 기반, 논 블로킹 I/O 모델을 구현하고 있음

---

## 이벤트 기반

이벤트가 발생할 때 미리 지정해둔 작업을 수행하는 방식

- 이벤트: 클릭이나, 네트워크 요청 등
- 특정 이벤트가 발생할 때 무엇을 할지 미리 등록
    - 이벤트 리스너에 콜백함수를 등록한다고 표현
- 노드는 다음 이벤트가 발생할 때까지 대기함

### 이벤트 루프

여러 이벤트가 동시에 발생했을 때 어떤 순서로 호출할지 판단

⇒ 노드가 종료될 때까지 이벤트 처리를 위한 작업을 반복하므로 루프(loop)라고 부름

```jsx
function first() {
	second();
	console.log('first');
}
function second() {
	third();
	console.log('second');
}
function third() {
	console.log('third');
}
first(); // third second first
```

![Untitled](/assets/images/post/211213/Untitled1.png)

⇒ anonymous : 처음 실행 시 전역 컨텍스트(global context) 의미 

context: 함수가 호출되었을 때 생성되는 환경

```jsx
function run(){
	console.log('3초 후 실행');
}
console.log('start');
setTimeout(run, 3000);
console.log('end');

// start end 3초 후 실행
```

- 백그라운드: setTimeout  같은 타이머나 이벤트 리스너들이 대기하는 곳, 여러 작업 동시 실행 가능
- 태스크 큐: 이벤트 발생 후, 백그라운드에서 태스크 큐로 타이머나 이벤트 리스너의 콜백함수를 보냄. 정해진 순서대로 콜백들이 줄을 서 있어 콜백 큐라고도 부름.

![setTimeout ⇒ anonymous ⇒ run 순으로 실행](/assets/images/post/211213/Untitled2.png)

setTimeout ⇒ anonymous ⇒ run 순으로 실행

## 논 블로킹 I/O

노드는 I/O 작업을 백그라운드로 넘겨 동시에 처리함

→ 동시에 처리될 수 있는 작업들은 최대한 묶어서 넘겨야 시간 절약

![Untitled](/assets/images/post/211213/Untitled3.png)

## 싱글 스레드

- 프로세스
    - 운영체제에서 할당하는 작업의 단위
    - 노드나 웹 브라우저 같은 프로그램은 개별적인 프로세스
    - 프로세스 간 메모리 등 자원 공유하지 않음
- 스레드
    - 프로세스 내에서 실행되는 흐름의 단위
    - 프로세스는 스레드를 여러개 생성해 여러 작업 동시 처리 가능
    - 부모 프로세스의 자원을 공유, 같은 주소의 메모리에 접근 간으하므로 데이터 공유 가능
- 노드 실행 시 프로세스 생성 그 후 내부적으로 스레드 여러 개 생성, 하지만 **직접 제어할 수 있는 스레드는 하나뿐**
- 스레드풀과 워커 스레드
    - 스레드풀 : 특정 동작 수행할 때 스스로 멀티 스레드 사용. 예) 암호화, 파일 입출력, 압축 등
    - 워커 스레드: 노드 12 버전에서 안정화된 기능으로 CPU 작업이 많은 경우 사용
    
    | 멀티스레딩 | 멀티 프로세싱 |
    | --- | --- |
    | 하나의 프로세스 안 여러개 스레드 | 여러 개의 프로세스 사용 |
    | CPU 작업 많을 때 | I/O 요청이 많을 때 |
    | 프로그래밍이 어려움 | 프로그래밍 비교적 쉬움 |