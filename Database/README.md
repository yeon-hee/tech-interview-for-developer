### Database
<br>

- [조인](#조인)
<br>


#### 조인

EMP table : 사원번호, 사원이름, 사원직책, 상관번호, 고용일, 월급, 커미션, 부서번호 등의 컬럼으로 구성됨

DEPT table : 부서번호, 부서이름, 부서위치 컬럼으로 구성됨


**Cross Join**

```java
SELECT *
FROM EMP, DEPT;
```
특정한 조건 없이 두 테이블 조인을 한 경우이다. 조건 없이 조인만 해서는 의미있는 데이터를 얻을 수 없다. 의미 있는 데이터를 얻기 위해 조건을 추가해서 조인을 해보자.
<br><br>

**Self Join**

한 테이블 내에서 조인

사원들의 이름과 함께 그 사원의 매니저 이름도 함께 알고 싶을 경우 셀프조인을 이용한다. 즉, employee 테이블, 자기 자신을 조인

```java
SELECT EMP1.empNo, EMP1.empName, EMP1.manager, EMP2.empName
FROM EMP EMP1 
JOIN EMP EMP2
ON EMP1.empNo = EMP2.manager
```
<br>

**Outer Join**

LEFT, RIGHT, FULL 세가지 종류

위의 결과에서는 사실 누락된 데이터가 있다. 해당 데이터들이 누락된 이유는 두 테이블간의 공통된 데이터가 없기 때문이다. 
예를 들어, '문정진'사원의 DEPTNO가 NULL이기 때문에 DEPT 테이블과 공통된 점이 없으며, '전산부' 또한 EMP 테이블에서 같은 부서 코드를 가진 데이터가 없기 때문에 출력되지 않는다. 하지만! 이러한 데이터들도 함께 보고싶은 경우가 있고 그런 경우 아우터 조인을 사용한다. 

먼저, 부서 코드가 NULL이거나 부서테이블의 DEPTNO와 일치하는 값이 없는 사원까지 출력하는 LEFT OUTER JOIN을 쿼리로 확인해보자.
<br>
<br>

**LEFT OUTER JOIN**

```java
SELECT EMP.empName, DEPT.deptName 
FROM EMP
LEFT OUTER JOIN DEPT
ON EMP.deptNo = DEPT.deptNo
```

위의 조인은 이너조인과 달리 '문정진' 사원의 데이터도 함께 나오는 것을 확인할 수 있다. 
<br>
<br>

**RIGHT OUTER JOIN**

EMP 테이블에서 같은 부서코드를 가진 데이터가 없는거까지 출력해주고 싶은 경우

```java
SELECT EMP.empName, DEPT.deptName
FROM EMP
RIGHT OUTER JOIN DEPT
ON EMP.deptNo = DEPT.deptNo
```
<br>

**FULL OUTER JOIN**

이 조인은 left 아우터 조인과 right 아우터 조인의 결과를 합친 것과 같다.

```java
SELECT EMP.empName, DEPT.deptName
FROM EMP
FULL OUTER JOIN DEPT
ON EMP.deptNo = DEPT.deptNo
```



