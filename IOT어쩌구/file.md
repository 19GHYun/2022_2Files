### 시작

![image](https://user-images.githubusercontent.com/94778099/189838403-a56a831d-2525-42f6-93cb-edb82b50e5e2.png)

캠핑장이 리눅스

나머지 구역은 리눅스. 임대하는데 마운트, 반납하는게 언마운트 라고 한다.

하나의 루트 디렉토리만 가지는 파일 시스템이라 여러 하드 디스크로 파티션을 나누기 위해서는 특정 폴더에 마운트를 한다..

![image](https://user-images.githubusercontent.com/94778099/189838723-92e3d381-0868-4bf5-bd26-6c18b7fd9887.png)

이런식으로 되어 잇다고 함. 윈도우랑 비슷하지만 살짝 다름.

리눅스의 기본 디렉토리 구조는 트리 구조다.

같은 목적의 파일들은 같은 장소에 일관되게 모아서 관리한다.


///


하드웨어 제어 방법.

유저 -> O/S -> 하드웨어  순서로 명령이 됨.

![image](https://user-images.githubusercontent.com/94778099/189840606-b336e554-6690-4c45-a704-4b6bb5d1e0a0.png)

///

리눅스 기본 명령어

date -> 현재 날짜 및 시간 확인

hostname -> 호스트 이름 확인

ls 명령어 -> 잘 알거라고 믿음

clear -> 잘 알거임

password -> 비밀번호 변경 할 수 있다.

홈 디렉토리 가는법 -> cd ~

그런데 사실 cd만 쳐도 가짐. 엄

홈디렉토리 가는 방법. -> cd home/pi , cd ~ , cd $HOME

직접경로와 상대경로 관련 나옴.

mkdir -> 디렉토리 만들기. 기본적으로 rwxr-xr-x .. 으로 설정이 되어잇다. 755엿나 이게

touch -> 빈 파일 생성, 존재하는 파일이면 수정시각을 바꿈.

ls cat head tail은 스킵 하셧다.

cp -> cp <복사할 대상><복사될 위치>  ex -> cp /home/pi/log.txt /home/pi/webapps/ 뭐 이런 절대경로도 되고,
편하게 상대경로도 된다.

. -> 현재 폴더, .. -> 상위 폴더.

mv -> mv <파일명><이동할 위치>

rm -> rm <파일명> 폴더를 지울려면 rm -r <디렉토리명>

파일 찾는 명령어

which -> which <명령어>  -> 특정 명령어의 위치를 전체 경로로 찾아주는 명렁어.

whereis -> whereis <파일명> -> 실행파일, 소스파일, man 페이지 파일의 위치를 찾아주는 명령어.

find -> find명령어를 통해 특정 이름을 가진 모든 파일과 디렉터리를 찾을 수 있다.

![image](https://user-images.githubusercontent.com/94778099/189845298-26603944-0a9b-493e-b441-4fc6fc61c06c.png)

슈퍼유저 해야 나오는 부분도 있는듯.

///

권한

chmod 750 <test.txt(요긴 수정할 파일이나 디렉토리)> 하면 test.txt의 권한이 바뀐다.

750 -> rwxr-x---

755 -> rwxr-xr-x..

sudo chown root:root test.txt

-> 소유주와 소유그룹의 이름을 바꿈. 슈퍼유저 권한이 있어야 실행이 가능.

///

ls > test.txt 하면 test.txt에 ls로 출력한 그게 test.txt에 작성이 됨.

///

라즈베리파이는 드럽게 느려서 wget를 써서 내려받으면 좋다.

git clone도 뭐 쓸 수 있는데.. 아무튼 그렇다.

라즈베리파이 파이썬 설치 해야함.

라즈비안에서 압축은 한번 읽어보자.tar로 압축을 한다는데 허허



---

기초 파이썬

..#할말 -> 한줄주석

"""
할
말
들
""" 
이러면 여러줄 주석. '''로도 가능함.

파이썬의 자료형

숫자형 문자형 있는데, 어차피 알아서 잡아준다고 함.

예를들면 a = 123, print(type(a)) 하면 자동으로 a가 int형으로 잡힌 걸 알 수 있음.

a = "파이썬" , print(type(a)) 하면 str타입을 리턴함.

리스트는 배열과 비슷한데, 길이 상관 없음, 서로 다른 타입끼리 가능, 중간이나 끝에 원소를 넣을 수 있고, 뺄 수 있음(이러면 자동으로 원소 정리해줌)

a,b,c,d = 0,0,0,0 그냥 이렇게 쉽게 리스트 되는듯.

![image](https://user-images.githubusercontent.com/94778099/190341318-dfb5459b-014d-4b6c-9251-aeaeeb259827.png)

이렇게도됨

```

aa = [30, 10, 20]

aa.append(50)

aa // aa출력 이러면 20뒤 마지막에 50이 추가되서 출력이 됨.

aa.pop() // 하면 50이 빠져나옴. 스택임 이거

aa.sort() // 하면 [10, 20, 30] 으로 정렬이 됨.

aa.reverse() // 내림차순

aa.remove(20) // 20이 빠짐. 결과는 [30,10]

bb = [1, 2, 3]

aa.extend(bb) // 하면  aa리스트에 [30, 10, 1, 2, 3]이렇게 됨.

aa.extend([4,5]) // 하면 aa리스트에 [30, 10, 1, 2, 3, 4, 5]가 된다.

```

물론 2차원 리스트도 가능하다.

![image](https://user-images.githubusercontent.com/94778099/190342164-51c4e30d-6a31-4750-a5e3-f0c38f55b81a.png)

리스트랑 비슷하지만 다른 튜플

다른점은 튜플 내부의 값을 바꿀 수 없다.

그거 뺴고 다 같음.

그리고 튜플은 소괄호로 표현이 됨.

```

card = (1,2,3) //이런식으로 표현하고,

card.append나, card.remove().. 이런게 불가능함.

```

튜플 수정 할려면? -> 튜플을 리스트로 바꾸는 함수를 쓴 후 수정하고, 다시 리스트를 튜플로 바꿔야 한다.


딕셔너리

c++에서 본거같은 사전

쓰는법

dict = {'번호':10, '성명':'장동건','나이':23,'사는곳':'서울'}

1대1 매치가 되어잇다.

![image](https://user-images.githubusercontent.com/94778099/190343411-f16ffdbc-0687-43ee-890f-1e8b4c4c7d9c.png)

*제어문

if문.

특징. if 뒤 괄호를 안씀

:클론을 이용해서 구분하고 그 다음 실행되어야 할 내용은 들여쓰기로 구분함.

![image](https://user-images.githubusercontent.com/94778099/190345201-e92e5e76-be0a-4e6e-b3d3-5fd1b62d9022.png)

for문도 똑같은데 생긴게 좀 다르다.

```

for i in range(10):
  print("aa")

```
이렇게 똑같이 : 랑 들여쓰기로 구분이 됨.

range뒤 상수는 그만큼 반복 되는 것이고,

range(1,10) -> i가 1부터 9까지 1씩 증가하면서 반복

range(0,5,1) -> i가 0부터 5까지 1씩 증가해서 반복, 0 1 2 3 4 로 반복이 됨.


while문

이것도 :와 들여쓰기로 구분이 됨.

while i<3:
  print...
  
i가 3번 반복됨. 0 1 2 일때.

이런 반복에 break; 넣어서 바로 반복을 끝낼 수 있다.


함수사용법

def 함수명():
(들여쓰기) 할 것.

![image](https://user-images.githubusercontent.com/94778099/190347644-42843a36-e9ab-4f02-9e1b-bef510d0c163.png)

인수2개쓰는건 한번 보자.

![image](https://user-images.githubusercontent.com/94778099/190347853-dd9e706f-77f6-44a3-89aa-c958d0edf2b6.png)


파이썬에서 클래스. 객체지향이라 잇을 수 밖에 없다.

```

class AutoMobile:
  name = ""
  velocity = 0
  def velocityPlus(self): // 여기서 self는 객체 자기 자신을 가르키는 c++로 치면 this-> 이런거
    self.velocity = self.velocity + 1
    print("속도는 %d 입니다." %self.velocity)
  def velocityDw(self):
    self.velocity = self.velocity -1
    if self.velocity < 0:
      self.velocity = 0
    print("속도는 %d 입니다.", %self.velocity)

ac = AutoMoblie(). // ac.name, ac.velocity가 생김.
ac.velocityPlus() // 속도는 1 입니다. 가 출력됨.
ac.velocity = 20
ac.velocityDw() //  속도는 19 입니다. 가 출력.

```

![image](https://user-images.githubusercontent.com/94778099/190349091-81ba7d5c-370f-45a3-9bd0-10204c8df9d4.png)

ac = AutoMoblie("소나타") 에서 소나타가 str로 들어간다.. 초깃값 있게 할려면 저렇게 self는 무조건 잇어야 한다.


모듈.

import math 하면 수학쪽 함수를 불러와서 쓸 수 잇다.

예를들면 print(round(3.14)) 이런걸 쓸 수 잇게 해줌.

추가로

module01.py 라는 파일에

def mydef01():
  print("일반함수다.")
def mydef02(n,m):
  print(n**m)

이런식으로 만들고, import module01 해도 가능하다.

이렇게 불러온 후 쓰는법은 이렇게

module01.mydef01()

module01.mydef02(10,20)
























