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


















