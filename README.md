# MBTI 봇

간단한 설명: 
누군가에게 자신의 성격 유형을 말해주면서 하나하나 외우는 건 무척 번거롭고 귀찮습니다. 테스트를 매번 하는건 말도 안되고, 결과를 스크린샷해서 찾아보기에는 뒤적이는 과정마저 귀찮죠.. (사진이 쌓일수록 해당 결과는 뒤로 갈 것입니다!) 그래서 만들었습니다. 그냥 성격 유형만 외웁시다. 그리곤 라인에서 친구 추가를 하고, 매번 궁금할 때 마다 성격 설명 또는 성격이라고 물어보세요. 그러면 그림과 함께 간단한 설명, 그리고 자세한 설명이 담긴 링크의 URL을 제공해줍니다!



## 주요 기능
1. MBTI 성격 유형 입력시, 설명 카드를 제공
2. 두 사람의 MBTI 성격 유형 입력시, 궁합을 알려줌
3. MBTI를 검사하고 싶다 (미구현)

## 실행 과정 

1. [Dialogflow](https://dialogflow.cloud.google.com/)에 접속하여 아래의 그림의 좌측에 보이는 Create new agent를 누르면 우측처럼 나옵니다. Agent name을 편하게 아무거나 짓고, Default language만 ko로 바꿔주세요. ![new agent](/source/1.png)

2. 이제 좌측에 보이는 MBTI 우측에 톱니바퀴(설정)을 눌러서 다음과 같이 Export and Import에 들어갑시다. 그리곤 Import From Zip을 누릅니다. ![톱니](/source/2.png) 

3. Zip파일을 드래그 드롭하고 밑에처럼 IMPORT를 꼭 적어주신 뒤 Import 클릭 ![import](/source/3.png)  

4. 위의 과정을 끝냈다면, ngrok-stable-windows-amd64를 설치합시다 (말이 설치지 인터넷에서 다운받으면 zip파일 압축해제한 것 뿐입니다. 같은 이름의 업로드한 폴더를 참조해주세요.) 설치 후 ngrok을 실행합니다. 그리고 ngrok http 5000을 실행합니다. 이 과정은 챗봇을 통해 들어온 파라미터들을 외부의 서버에 보내기 위해 외부서버와 로컬서버를 잇는 가상의 접속주소를 제공합니다. ![ngrok1](/source/4.png)

5. 출력된 Forwarding란에서 https로 시작하는 주소를 복사합니다. ![ngrok](/source/5.png)

6. 복사한 주소를 다시 Dialogflow에 가서 왼쪽 Fullfillment 탭 누르고, 오른쪽 Webhook Enabled로 바꾼 뒤, URL에 복사한 주소를 붙여 넣기하고 /webhook을 추가한뒤 save합니다. 

7. 이제 line과 연동을 해봅시다. 이를 위해서는 [Line Developers](https://account.line.biz/login?redirectUri=https%3A%2F%2Fdevelopers.line.biz%2Fconsole%2Fchannel%2F1654458386%2Fmessaging-api&scope=line)에 접속하여 로그인을 한 후,

