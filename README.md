# 🤿 CO2 Table Maker

[![홈 이미지](https://sanggusseu.github.io/co2table-maker/og-image.jpg)](https://sanggusseu.github.io/co2table-maker/)

## ✨ 프로젝트 소개

- CO2 Table Maker는 프리다이빙 훈련을 위한 CO2 테이블을 생성하는 웹 애플리케이션입니다.
- 사용자는 훈련 시간과 호흡 시간을 입력하면 개인 맞춤형 CO2 테이블을 생성할 수 있습니다.
- 이 프로젝트를 통해 **Quasar를 활용한 반응형 웹 개발**과, **Pinia를 활용한 상태 관리**를 배웠습니다.

## 🛠 사용한 기술

- **Quasar** - Vue.js 기반의 퀘이사 프레임워크를 활용하여, 직관적이고 반응형인 사용자 인터페이스를 구현하였습니다.
- **Pinia** - 상태 관리를 위해 Vue 3의 새로운 상태 관리 라이브러리인 Pinia를 사용하여, 데이터 상태의 효율적 관리와 컴포넌트 간 데이터 공유를 구현했습니다.

## 📌 이슈

- 숨 참기 기록 입력란에서 음수 입력이 가능한 문제
- 자식 컴포넌트의 상태를 부모 및 형제 컴포넌트에서 사용할 수 없다는 문제

## ✨ 해결 및 성과

- 기본 HTML 속성 `input type="number" min="1"`을 사용하여 음수 입력을 방지하고자 했으나, 이는 완벽한 해결책이 아님. 그래서 스크립트를 추가하여 사용자가 숫자, 삭제, .만 입력할 수 있도록 개선
- Pinia로 record 상태를 전역으로 관리하여 부모 컴포넌트에서도 사용할 수 있도록 개선

## 📚 배운 점

- HTML의 기본 제공 속성만으로는 모든 기능을 완벽하게 구현할 수 없음을 깨달음. 앞으로는 기본 속성이 실제 요구사항에 부합하는지 항상 검토하겠다고 다짐.
- Pinia의 유용성을 다시 한번 인지하게 됨

## 🚀 주요 기능

- **숫자, 삭제, .만 입력 가능한 기능**: 기존 input type="number" min="1"을 사용하니, 음수가 입력 가능한 이슈가 발생하여, 스크립트를 추가 작성하여 숫자, 삭제, .만 입력 가능하게 만들었습니다.
  `RecordForm.vue`

  ```js
  // .. 생략

  const handleOnkeyDown = e => {
    const num = e.key * 1;
    const exclude = ['Backspace', 'Delete', '.'];
    if (exclude.includes(e.key)) return;
    if (isNaN(num)) e.preventDefault();
  };

  // .. 생략
  ```

- **Pinia로 record 상태 관리**: `RecordForm`에서 `record` 상태를 관리하면 부모 컴포넌트에서 사용하지 못하여 `Pinia`로 관리했습니다.
