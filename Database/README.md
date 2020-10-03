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

**Self Join**

한 테이블 내에서 조인

사원들의 이름과 함께 그 사원의 매니저 이름도 함께 알고 싶을 경우 셀프조인을 이용한다. 즉, employee 테이블, 자기 자신을 조인

```java
SELECT EMP1.EMPNO, EMP1.EMPNAME, EMP1.MANAGER, EMP2.EMPNAME
FROM EMP EMP1 
JOIN EMP EMP2
ON EMP1.EMPNO = EMP2.MANAGER
```

**Outer Join**

