# object 클래스
* 모든 클래스는 object 클래스를 상속받음
* Python 2.2부터 old style class와 new style class를 구분하기 시작함
  * old style class는 "class 클래스명:"으로 선언함
  * new style class는 "class 클래스명(object):"로 선언함
* Python 3.x에서 new style class는 "class 클래스명(object):"으로 선언하며, 이는 "class 클래스명:"으로도 나타낼 수 있음
  * Python 3.x부터는 old style class는 존재하지 않음
  * 그런데 object를 명시하지 않고 "class 클래스명:" 으로 선언할 시 old style class와 동일한 형태가 됨
  * 만약 해당 코드를 Python 2.x에서 쓸 경우 old style class로 간주될 수 있음. 호환성을 위해 (object)를 명시하는 것이 권장됨
