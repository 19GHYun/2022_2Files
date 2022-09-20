## 2022_09_20

### 라즈베리파이를 위한 전자기초

배우는게 옴의법칙, 키르히호프법칙, 데이터시트확인, 전자회로 보고 브레드보드 연결, 전자부품 특성 알아보기. 가 있다.

#### 전기회로

회로가 연결되어 있으면 닫힌회로(closed Circuit) 또는 폐회로 라고 하고

전선이 끊어져 잇으면 열린 회로라고 한다(Open Circuit). 헷갈리지 않게 조심

![image](https://user-images.githubusercontent.com/94778099/191191251-7430a8f2-4c62-4aa0-9a11-e9f7b2cdd48a.png)


전자와 전류의 흐름을 잘 보자. 전자는 +에서 -로, 전류는 -에서 +로 흐름.



#### 전압 전류 저항.

전압 : 전류가 흐를때의 힘을 나타내는 물리량  - 기호 V(Voltage) 단위 V(볼트)
  
전류 : 전선을 통해 흐르는 전기의 물리량   - 기호 I(Intensity) 단위 A(암페어)

저항 : 전기의 흐름을 방해하는 정도를 나타내는 물리량.. -  기호 R(Resisance)  단위는 옴.

![image](https://user-images.githubusercontent.com/94778099/191191721-83dae3a9-9ec2-4abf-bba2-651c360bd3fa.png)



#### 옴의법칙

한줄요약

V = I * R  전압은 전류 곱하기 저항

![image](https://user-images.githubusercontent.com/94778099/191192083-328ce407-22f9-438b-9f3c-10e7b7af9f44.png)



![image](https://user-images.githubusercontent.com/94778099/191192209-30570fe8-38d0-4426-83b0-b940448af63c.png)

답은 2암페아.

12 = ? * 6 이니까..

#### 키르히호프의 법칙.

1.전류의 법칙

폐회로에서 접속점(Node)를 통해 들어오는 전류와 나가는 전류의 합은 같다.

![image](https://user-images.githubusercontent.com/94778099/191192520-5ffd0d3b-c34b-4bde-a39e-8728a891a881.png)

들어오는 전류 I1 I2 I3 합친것은 나가는 전류 I4 I5를 합친거와 같다.



2. 전압의 법칙

폐회로의 전원전압의 합은 폐회로내의 전압강하의 합과 같다.

![image](https://user-images.githubusercontent.com/94778099/191192720-be16d69d-7b10-489e-a1a1-9b9cdaa0c10b.png)

*전압강하* - 전압이 인가되고...

https://oasisfores.com/kcl-kvl/

여기 보고 배우자


### 브레드보드

이거임.

![image](https://user-images.githubusercontent.com/94778099/191194091-a61bf219-5a70-43e0-a162-2f6c9de0f782.png)

빨간선 + 파란선 - 프린팅 되어잇다. + - 표시에 전원 연결해서 저기다가 꽂아서 쓸수 잇는 멀티탭같은 그런거다.



#### 예제

![image](https://user-images.githubusercontent.com/94778099/191194806-dab73aff-6ee3-4820-a8cb-d29d23d5106b.png)

다 더하면 60옴.  V = IR 에서 I는 0.2가 나옴.

R2 는 0.2 * 20 = 4볼트. R1는 2볼트 R3는 6볼트 다해서 12볼트.


#### 저항 용량 읽는법

![image](https://user-images.githubusercontent.com/94778099/191195484-3581c929-1c9c-4496-aba6-eedbb88860ac.png)

오른쪽 예시에 보면 갈색 = 1, 검은색 = 0. 

10 * 그다음 갈색 10. = 100. 그 다음 금색 -> 오차가 +-5%.


#### LED 극성

![image](https://user-images.githubusercontent.com/94778099/191195864-ef488b00-6b51-4262-b88e-c68d9fd7920b.png)

긴곳이 + 짧은쪽이 - 에 꽂아야 함.

반대로 연결하면 바로 골로감.

한쪽 방향으로 흐르는게 다이오드?



#### 이렇게 브레드보드를 쓴다.

![image](https://user-images.githubusercontent.com/94778099/191196447-098b6468-cb67-49b5-8ec4-c4575abefdae.png)


#### LED와 저항회로 구성

![image](https://user-images.githubusercontent.com/94778099/191196761-e45c5b1e-94aa-4f32-aec5-ad9b7278f8af.png)

Forward Voltage 정방향으로 흐를때 동작하는 범위가 1.8V부터 2.2V까지. 만약 10V에 꽂아서 작동하게 할려면 저항을 넣어야한다..

If = 20mA -> 20mA에 버틴다는 뜻인듯


wavlenength 파장 -> 약간 파장에 따라 나오는 색이라고 생각. 620에서 625뭔 뭐 노란색이다 이런식으로 쓰임.

이 친구는 2볼트에 20mA에서 잘 작동되는 구나 이렇게 해석이 됨.


![image](https://user-images.githubusercontent.com/94778099/191197571-fe3ec1e5-949a-4b9c-b7f3-ec1432c0d698.png)


5V에서 2V는 LED가 쓰니까. R에 걸려야 하는 전압은 3V - 키르히호프의 전압의 법칙.

I는 0.02A. 20mA임.

V = iR 에서 3 = 0.02 * R 이 된다. 그럼 R은 150옴이 됨. < 제일 최적의 옴.



#### push 버튼 스위치.

![image](https://user-images.githubusercontent.com/94778099/191198739-ea902b40-251f-4116-bb51-450cea435000.png)

그냥 발이 4개지 스위치 역할을 한다.


#### 콘덴서

![image](https://user-images.githubusercontent.com/94778099/191199346-3c7c14dc-7b60-4a6a-ac95-08257a806775.png)

무조건 다리가 긴게 + 짧은게 -

기호로는 저렇게 3개로 표현

콘덴서는 전기를 저장한다...

전기가 저장되는 동안 전압과 전류가 흐르다가, 다 저장되면 끊긴다. 근데 이건 직류고

교류에선 다르다.

교류에선 우리나라로 치면 220v가 60헤르츠로 + - 로 왔다갓다 하면서 흐르기 때문에, 콘덴서에서 전류 전압 충전하면서 뭐 그렇게 잘 된다..

그래서 콘덴서의 특징이 직류는 차단하고 교류는 통과하는 것 이다.

DC - 직류 AC - 교류

![image](https://user-images.githubusercontent.com/94778099/191202374-e22f3163-3a66-45af-9d17-bc81836cc9d3.png)


불이 천천히 밝아지는 회로임 근데 왜?

-> LED에 손상을 방지하기 위해.

스위치를 딱 닫으면 5v여도 순간적으로 팍 튀엇다가 안정이 됨. 그 순간 손상을 받을 수 잇기 때문에..

저항이 1옴이라도 잇으면 그쪽으로 안 흐를려는 성질이 있다. 그럼 커패시터쪽으로 가는데,  전압이 차고 전류가 떨어지면서 끊김. 이제 그 다음으로 저항이
있는 곳으로 가져서 LED가 켜진다...


#### 트랜지스터

트랜지스터는 반도체를 이용하여 전자 신호, 및 전력을 증폭하거나 스위칭 하는데 사용되는 반도체 소자이다.

-보통 스위칭 할때 쓰인다고 함.


![image](https://user-images.githubusercontent.com/94778099/191203394-65203f96-8a8b-446f-bfae-1cc9be2e43b2.png)


C - 콜렉터 전류가 들어오는 곳

E - 에미터 출구

B - 스위치랑 비슷한 그런거.

스위치는 약간 물리적인 거라면, B에 신호를 주면 C와E가 통하게 하는 그런 것.

#### 다이오드

방금 본거처럼 +에서 -로 흐르며, 반대로 흐를 시 막아준다.

![image](https://user-images.githubusercontent.com/94778099/191203884-f239775b-d96b-4a5a-8435-e1a4a178c029.png)

다이오드 지날때 살짝 전압이 떨어진다? 

![image](https://user-images.githubusercontent.com/94778099/191204434-3fc351af-a6f0-4c15-b894-81890650da12.png)


아무리 다이오드여도, 일정 전압 넘기면 역전압을 못막는데, 이 위치를 항복전압이라고 한다. 그림엔 -50V정도되는듯

![image](https://user-images.githubusercontent.com/94778099/191204552-8ca635af-019a-40a4-9b4c-cabf862d96cc.png)
















