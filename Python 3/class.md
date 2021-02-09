# @classmethod와 @staticmethod
* 객체를 생성하지 않고 클래스에서 바로 호출함

## @classmethod
* 첫 번째 매개변수로 클래스의 참조변수(보통 cls)를 받음
* 참조변수 cls를 통해 메서드 내에서 클래스 변수와 다른 클래스 메서드에 접근할 수 있음(접근할 필요가 있을 때 classmethod 사용)

## @staticmethod
* @classmethod와 달리 클래스에 대한 참조변수를 매개변수로 받지 않아 인스턴스 속성은 물론, 클래스 속성에도 접근할 수 없음
  (staticmethod 내에서 객체를 생성하여 인스턴스 속성 및 메서드에 접근 가능, 클래스를 통해 클래스 속성 및 메서드에 접근 가능)
* 매개변수로 받은 변수들만 다루므로 굳이 클래스 내에 선언할 필요는 없지만, 그럼에도 클래스 내부에 같이 묶어두고자 할 때 staticmethod 사용

# object 클래스
* 모든 클래스는 object 클래스를 상속받음
* Python 2.2부터 old style class와 new style class를 구분하기 시작함
  * old style class는 "class 클래스명:"으로 선언함
  * new style class는 "class 클래스명(object):"로 선언함
* Python 3.x에서 new style class는 "class 클래스명(object):"으로 선언하며, 이는 "class 클래스명:"으로도 나타낼 수 있음
  * Python 3.x부터는 old style class는 존재하지 않음
  * 그런데 object를 명시하지 않고 "class 클래스명:" 으로 선언할 시 old style class와 동일한 형태가 됨
  * 만약 해당 코드를 Python 2.x에서 쓸 경우 old style class로 간주될 수 있음. 호환성을 위해 (object)를 명시하는 것이 권장됨
