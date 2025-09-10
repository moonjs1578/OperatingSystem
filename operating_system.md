# Operating System

## CH02

---

### Operating System Objectives
- **Convenience** : 사용 편의성 제공  
- **Efficiency** : 시스템 자원 효율적 사용  
- **Ability to evolve (발전성)** : 새로운 기능과 하드웨어 지원 가능

---

### Layers of Computer System
**Software**
- Application programs  
- Libraries / Utilities  
- Operating system  

**Hardware**
- Execution hardware 
- System interconnect (bus)  
- Memory translation: 가상 메모리 → 물리적 메모리  
- I/O devices and networking  
- Main memory  

---

## Services Provided by Operating System
- **Program development**  
  - Editors (코드 작성 도구)  
  - Debugger (오류 수정 도구)  
- **Program execution**  
  - 프로그램 실행, 자원 관리, 스케줄링  
- **Access to I/O devices**  
  - 여러 장치와 사용자의 동시 접근 관리  
- **Controlled access to files**  
  - 다중 사용자 환경에서 자원 보호 및 동시성 관리  
- **Accounting**  
  - 사용 통계 수집, 성능 모니터링  
  - 미래 개선 방향 예측  
  - 과금 목적 활용  
- **Error detection and response**  
  - Hardware errors: Memory error, Device failure  
  - Software errors: Arithmetic overflow, Division by zero, Forbidden memory access  
  - OS가 처리할 수 없는 애플리케이션 요청

---

### Operating System as Resource Manager
- **Resources**: Processor(CPU), Memory, I/O 등  
- OS는 **자원 관리 책임**을 가짐  
- OS도 일반 소프트웨어처럼 **CPU에 의해 실행되는 프로그램**  

---

### Ease of Evolution of an Operating System
- **Hardware upgrades**  
  - 새로운 하드웨어와 기존 하드웨어 지원  
  - MMU(Memory Management Unit) → Paging mechanism(메모리 효율적 관리)  
- **New services**  
  - Windows, GUI(Graphical User Interface) 등  
- **Fixes**  
  - 버그 수정  
  - **The fix may introduce new faults**: 수정이 새로운 결함을 발생시킬 수 있음  

---

### Operating System (OS)
- OS = **Kernel + System Programs**
  - **Kernel**: 메모리에 상주, 시스템 부팅 시 메모리에 설치되는 함수 집합  
  - **System Programs**: 디스크에 존재, 설정/제어판 프로그램 등  
- **Kernel 호출 시점**
  - 응용 프로그램에서 API 함수 호출  
  - I/O 장치에서 데이터 도착

---

### Evolution of Operating Systems

#### Multiprogramming
**CPU가 제어권을 넘기는 경우**
1. 현재 실행 중인 프로그램이 I/O 함수를 호출했을 때 → 프로세스가 스스로 CPU 포기  
2. I/O 장치에 기다리던 데이터가 들어왔을 때 → 외부 이벤트가 프로세스를 깨움  
3. 현재 실행중인 프로그램이 time slice 동안 계속 CPU 사용 → 타이머 인터럽트로 선점  


```
New → Ready ──(스케줄러)──▶ Running
                ▲                │
                │                ▼
              ◀─ Ready ◀─(I/O 완료)── Waiting(Blocked)
                                   │
                                   └─(프로세스 종료)→ Terminated
```
Ready(준비) : CPU를 받을 준비가 된 상태(실행 대기 큐).

Running(실행) : 실제 CPU를 할당받아 실행 중.

Waiting/Blocked(대기) : I/O 같은 이벤트를 기다리며 CPU를 사용하지 않는 상태.

I/O가 완료되면 OS가 해당 프로세스를 Ready로 이동시킴.

#### Multiprogramming vs Time Sharing
- Multiprogramming
   - Maximize processor use(CPU 활용 최대화)
- Time Sharing
   - Minimize response time



