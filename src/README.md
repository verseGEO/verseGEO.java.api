## 1. Exchange Rate API (제휴사 → verseB)

Exchange Rate 조회 API는 게임 또는 서비스의 Item, Point등에 대한 Play Token 변환 전 반드시 호출해 환율을 참조해야 합니다. Exchange Rate 조회를 통해 참조된 환율은 후속 API인 “Exchange 요청 API”에 적용되어 Play Token으로 전환 가능합니다.

* Java API Interface Specification

| API | JAVA API |Note|
|-----|----------|----|
|Exchange Rate API|VerseB.exRate|HashMap<String, String> hmOut =-VerseB.exRate(HashMap<String, String> hmIn);|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/ExchangeRateSeq.png">



## 2. Exchange Request API (제휴사 → verseB)

Exchange Rate 조회 후 수신된 환율기준으로 Item 또는 Point를 Play Token으로 전환 요청합니다. 이때 Play Token용 주소가 미발급 상태이면 verseB 측에서 Play Token 주소를 자동할당 하게 됩니다. 전환하게 될 Item 또는 Point는 Exchange Rate 조회에서 수신된 환율에 따라 해당 수량을 계산하여 수량이 최소 수량 이하이면 거래 불가에 대한 안내를 수행해야 합니다.

* Java API Interface Specification

| API | JAVA API |Note|
|-----|----------|----|
|Exchange Request API|VerseB.exReq.json|HashMap<String, String> hmOut =-VerseB.exReq(HashMap<String, String> hmIn);|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/ExchangeRequestSeq.png">



## 3. P2E Withdrawal Address Verification API (제휴사 → verseB)

P2E 출금주소 검증 요청은 Game 또는 Contents 등 Metaverse 생태계 내부에서 먼 사용 가능한 Play Token을 블록체인 Public Chain에 전송하기 위해 필요한 Ethereum 주소의 정합성을 검증하는 기능입니다. P2E 출금주소 검증은 주소의 정당성 여부만 Check 합니다. 이에 따라 사용자는 P2E 출금주소를 반드시 정확히 입력해야 합니다.

* Java API Interface Specification

| API | JAVA API |Note|
|-----|----------|----|
|Withdrawal Address Verification API|VerseB.OutAddrVerify|HashMap<String, String> hmOut =-VerseB.OutAddrVerify(HashMap<String, String> hmIn);|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/WithdrawalAddressVerificationSeq.png">



## 4. P2E Password Registration API (제휴사 → verseB)

P2E 출금을 위해서는 사용자 비밀번호 등록이 필요합니다. 제휴사는 사용자에게 비밀번호를 입력 받아 검증후 저장합니다. 또한 등록 비밀번호는 verseB에 등록 요청을 하여 제휴사에서 1회, verseB에서 2회 검증하여 진행합니다. verseB에 등록되는 비밀번호는 제휴사에서 암호화한 비밀번호를 2차 암호화(단방향)여 적용합니다.

* Java API Interface Specification

| API | JAVA API |Note|
|-----|----------|----|
|Password Registration API|VerseB.OutPaswordReg|HashMap<String, String> hmOut =-VerseB.OutPaswordReg(HashMap<String, String> hmIn);|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/PasswordRegistrationSeq.png">



## 5. P2E Withdrawal API (제휴사 → verseB)

P2E 출금은 Play Token을 외부 이더리움 주소로 전송하는 기능입니다. 외부 이더리움 주소 전송된 P2E Token은 거래소 등 다양한 분야에 자유롭게 사용 가능합니다.

* Java API Interface Specification

| API | JAVA API |Note|
|-----|----------|----|
|Withdrawal API|VerseB.WithdrawReq|HashMap<String, String> hmOut =-VerseB.WithdrawReq(HashMap<String, String> hmIn);|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/WithdrawalSeq-1.png">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/WithdrawalSeq-2.png">



