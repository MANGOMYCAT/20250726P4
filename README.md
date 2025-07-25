<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>사회정서 역량 체크리스트</title>
  <style>
    body {
      font-family: 'Noto Sans KR', sans-serif;
      background-color: #f0f4f8;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 20px;
    }
    .container {
      width: 100%;
      max-width: 1000px;
      background-color: white;
      border-radius: 15px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      padding: 30px 40px;
    }
    .header h1 {
      font-size: 24px;
      color: #1a237e;
      margin: 0;
      font-weight: 700;
    }
    .tab-nav {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      margin: 20px 0;
      gap: 10px;
    }
    .tab-button {
      flex: 1 1 30%;
      padding: 10px;
      background-color: #f9f9f9;
      border: 1px solid #ccc;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      text-align: center;
      transition: background-color 0.3s;
    }
    .tab-button.active {
      background-color: #ff8a80;
      color: white;
      border-color: #ff8a80;
    }
    .tab-content {
      display: none;
    }
    .tab-content.active {
      display: block;
      margin-top: 20px;
    }
    ul {
      list-style-type: disc;
      padding-left: 20px;
    }
    li {
      margin-bottom: 10px;
      font-size: 15px;
    }
  </style>
</head>
<body>
  <div class="container">
    <header class="header">
      <h1>사회정서 역량 체크리스트</h1>
    </header>

    <nav class="tab-nav">
      <button class="tab-button active" data-tab="self-awareness">자기인식</button>
      <button class="tab-button" data-tab="self-regulation">자기조절</button>
      <button class="tab-button" data-tab="social-awareness">관계인식</button>
      <button class="tab-button" data-tab="relationship-management">관계관리</button>
      <button class="tab-button" data-tab="community-values">공동체 가치</button>
      <button class="tab-button" data-tab="mental-health">마음건강</button>
    </nav>

    <main>
      <div id="self-awareness" class="tab-content active">
        <ul>
          <li>내가 발표할 때 긴장된다는 걸 알아차림</li>
          <li>내가 어떤 상황에서 스트레스를 받는지 인식함</li>
          <li>자신이 화날 때 몸의 반응을 말로 설명함</li>
          <li>'나는 지금 집중이 안 되고 있어'라고 스스로 말함</li>
          <li>자신의 강점과 약점을 구체적으로 알고 있음</li>
        </ul>
      </div>

      <div id="self-regulation" class="tab-content">
        <ul>
          <li>화가 났을 때 한숨을 쉬며 진정함</li>
          <li>시험 전 불안을 줄이기 위해 명상함</li>
          <li>게임 시간을 스스로 조절하고 약속을 지킴</li>
          <li>부정적인 생각을 긍정적으로 바꾸려 노력함</li>
          <li>과제를 미루지 않고 계획대로 수행함</li>
        </ul>
      </div>

      <div id="social-awareness" class="tab-content">
        <ul>
          <li>친구가 속상해 보일 때 먼저 다가감</li>
          <li>다른 친구의 문화적 배경을 존중함</li>
          <li>상대방의 입장을 이해하려 노력함</li>
          <li>친구가 기뻐할 때 함께 기뻐함</li>
          <li>타인의 말이나 표정을 보고 감정을 짐작함</li>
        </ul>
      </div>

      <div id="relationship-management" class="tab-content">
        <ul>
          <li>의사소통이 잘 안될 때 다시 설명함</li>
          <li>친구와 다툰 후 먼저 사과함</li>
          <li>갈등이 생겼을 때 중재를 시도함</li>
          <li>협동활동에서 역할을 조율함</li>
          <li>말다툼 대신 차분하게 자신의 입장을 표현함</li>
        </ul>
      </div>

      <div id="community-values" class="tab-content">
        <ul>
          <li>운동장 순서를 지켜 사용함</li>
          <li>학급 규칙을 함께 만들어 지킴</li>
          <li>친구의 실수를 감싸주며 함께 책임짐</li>
          <li>역할 분담에서 자신에게 맡겨진 일을 성실히 함</li>
          <li>다른 친구가 소외되지 않도록 배려함</li>
        </ul>
      </div>

      <div id="mental-health" class="tab-content">
        <ul>
          <li>슬프거나 불안할 때 선생님께 도움 요청함</li>
          <li>자신이 우울한 기분임을 인식하고 일기를 씀</li>
          <li>스트레스를 받을 때 음악이나 운동으로 해소함</li>
          <li>혼자나 폭력에 대한 잘못된 정보를 비판적으로 바라봄</li>
          <li>자신의 정신 건강을 지키기 위해 휴식시간을 가짐</li>
        </ul>
      </div>
    </main>
  </div>

  <script>
    const tabButtons = document.querySelectorAll('.tab-button');
    const tabContents = document.querySelectorAll('.tab-content');

    tabButtons.forEach(button => {
      button.addEventListener('click', () => {
        tabButtons.forEach(btn => btn.classList.remove('active'));
        button.classList.add('active');

        tabContents.forEach(content => content.classList.remove('active'));
        const targetTab = button.getAttribute('data-tab');
        document.getElementById(targetTab).classList.add('active');
      });
    });
  </script>
</body>
</html>
