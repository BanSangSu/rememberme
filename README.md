# rememberme
start-app
SW중심 사업단 2021-10-29 ~ 2021-10-31

#맞춤형 복지정책 정보 제공 시스템

#Outline
1. 사회적 약자들이 정부 기관에서 운영하는 사업을 접허기 쉽게하는 정보 제공 서비스 앱

#Benefit
1. 정부 홍보비를 통한 외주비
2. 정부 사업 자료 대행을 통한 수수료

#Progress
1. 약자마다 카테고리를 나눌 수 있는 메뉴 제공
2. RecyclerView를 사용하여 정책 정보 출력
3. 세부사항을 타이핑이나 음성인식 기능을 이용하여 검색할 수 있다.
4. Reminder기능을 이용하여 알림 푸쉬메시지를 출력

#TroubleShooting
1. 권한에 따라 작성, 보기 기능으로 텍스트를 접할 수 있지만 보기 기능을 사용하면 hyperlink 또한 접근하지 못했다. -> 보기 기능만을 제공해주었다. ->> 보기 layout과 작성 layout를 나눠서 제공해야겠다.
2. 카테고리를 나누는 과정에서 SQLite를 다루는 DAO부분이나 DTO 부분과 같은 내부 code가 read-only라 변경하지 못하여 DB의 모든 인원들을 세부사항 별로 분류하지는 못했다. -> 남은 DB column을 통해 데이터를 DB에 넣어 놓은 뒤 소수의 인원들을 어느정도만 분류하고, boolean값을 통해 특직을 넘겨주는 기존의 코드를 활용하여 정보를 분산시켰다. ->> Firebase나 개인 DB를 구축하여 생산성과 확장성을 높일 생각이다.
3. 내무 DB에서 사진이 저장되어 나갔다 들어와도 사라지지는 않았지만 강제로 DB만 따로 빼서 build시키자 사진 데이터만 받아오지 못했다. -> DB를 가져온 다음 사진을 찍어 업로드 했다. ->> 안정적인 DB를 구축하여 외부에서도 여러 컨텐츠를 정확하게(Integrity) 저장하고 사용할 수 있도록 만들어야겠다.
4. 음성인식기능을 Fragment에 생성하고 정보를 전달하여 외부 아이콘으로 뺄 계획이었다. -> Fragment끼리 정보를 잘 전달하지 못했고, 프로그램 실행에 문제가 생겨 검색기능에서 제공하는 음성인식기능을 사용하였다. ->> 외부 위치로 빼는 것 뿐만 아니라 시각장애인을 위한 UI/UX를 제공할 생각이다.

#Other future
1. 사용자의 거주 및 지역 정보를 받아 지역에 따른 사업이나 위치에 따른 혜택 정보를 제공한다.
2. 사용자의 동의를 얻고 상태 정보를 획득한 뒤 그에 맞는 정보를 제공한다.
3. Web crawling을 통해 저웁 사업들의 정보를 실시간으로 가져온다.
4. 혜택을 받는데 필요한 서류와 같은 복잡한 절차를 해소시켜주는 서비스를 제공한다.  
5. 데이터를 기반으로 사업에 따라 어떤 자료가 필요하고 어떤식으로 준비하면 좋은지 진행 및 추천 방법을 제공한다.
6. 빅데이터를 통해 헤택을 받는 사람들을의 성향을 파악하여 앞으로의 도시 비용을 예측하고 준비하는 정보 제공서비스를 기관에게 제공한다.
