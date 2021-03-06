### DB 정규화란 무엇인가요?

테이블이 잘 만들어졌는지 확인하고, 잘 만들지 못한 테이블을 고쳐나가는 과정입니다. 테이블을 정규형이라고 불리는 형태에 부합하게 만들어가는 과정입니다. **테이블간 무결성을 유지할 수 있고, DB 의 저장 용량을 줄일 수 있습니다.**

정규형은 1NF, 2NF, 3NF 의 순서에 따라 규칙이 누적됩니다.

### 제 1 정규화에 대해서 설명해주세요.

테이블의 컬럼이 원자값을 갖도록 테이블을 분해하는 것 입니다.

### 제 2 정규화에 대해서 설명해주세요.

제 1 정규화를 진행한 테이블에 대해 `완전 함수 종속`을 만족하도록 테이블을 분해하는 것입니다. **완전 함수 종속은 기본키의 부분집합이 결정자가 되어서는 안되다는 것**을 의미합니다. 만약 수강강좌 테이블에서 학생 번호와 강좌 이름이 기본키이고, 강의실과 성적을 결정한다고 했을 때 강의실은 기본키의 부분키인 강좌이름이 결정하기 때문에 이 테이블을 분해해야합니다.

함수 종속 : A 어트리뷰트가 B 어트리뷰트의 결정자이면, B 가 A 에 함수적으로 종속한다고 말한다. B → A

### 제 3 정규화에 대해서 설명해주세요.

제 2 정규화를 진행한 테이블에 대해 `이행적 종속`을 없애도록 테이블을 분해하는 것입니다. 이행적 종속은 A → B → C 가 성립할 때, A → C 가 성립되는 것을 의미합니다. 학생 번호, 강좌 이름, 수강료로 테이블을 구성했을 때 학생 번호 강좌 이름, 강좌 이름 수강료의 참조관계만으로도 테이블을 만들 수 있습니다.

### BCNF 정규화에 대해서 설명해주세요. (Boyce-Codd Normal Form)

제 3 정규화를 진행한 테이블에 대해 **모든 결정자가 후보키**가 되도록 테이블을 분해하는 것입니다.

학생번호와 강좌이름이 기본키이며, 교수님을 결정한다고 했을 때, 교수님이 강좌이름에 대한 결정자가 됩니다. 따라서 교수님이 후보키가 되기 위해서 테이블을 분리해야합니다.

후보키 : 기본키(PK)로 사용할 수 있는 속성들의 부분 집합

결정자 : 어떤 애트리뷰트의 값이 다른 애트리뷰트의 값을 고유하게 결정함.

### REFERENCE

[[Database] 정규화(Normalization) 쉽게 이해하기](https://mangkyu.tistory.com/110)

[[DB기초] 여러가지 키(기본키,후보키,외래키등)의 종류와 개념](https://coding-factory.tistory.com/220)
