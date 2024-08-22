# CO2 Table Maker

[![홈 이미지](https://sanggusseu.github.io/co2table-maker/og-image.jpg)](https://sanggusseu.github.io/co2table-maker/)

## ✨ 프로젝트 소개

- CO2 Table Maker는 프리다이빙을 준비하는 사람들을 위한 웹 사이트입니다. 프리다이빙 레벨 1을 취득하기 전, 숨 참기 훈련을 통해 이산화탄소 내성을 높이는 것이 중요한데, 이 사이트는 이러한 훈련에 필요한 맞춤형 CO2 Table을 자동으로 생성해 줍니다. 사용자는 자신의 숨 참기 최고 기록을 입력하기만 하면, 그에 맞는 CO2 Table을 받아볼 수 있어 손쉽게 훈련을 시작할 수 있습니다.

## 🛠 사용한 기술

- **Quasar** - Vue.js 기반의 퀘이사 프레임워크를 활용하여, 직관적이고 반응형인 사용자 인터페이스를 구현하였습니다.
- **Pinia** - 상태 관리를 위해 Vue 3의 새로운 상태 관리 라이브러리인 Pinia를 사용하여, 데이터 상태의 효율적 관리와 컴포넌트 간 데이터 공유를 구현했습니다.

## 📚 학습 내용 및 구현 기능

#### 1. Quasar를 활용한 반응형 웹 개발

- Quasar는 Vue.js 기반의 프레임워크로, 빠르고 반응형인 UI를 손쉽게 구축할 수 있는 도구입니다. 이 프로젝트에서는 Quasar의 컴포넌트 시스템을 활용해 직관적이고 효율적인 사용자 인터페이스를 구성했습니다.
- Quasar의 `q-input`, `q-table`와 같은 UI 컴포넌트를 이용하여 사용자가 간편하게 숨 참기 기록을 입력하고, 맞춤형 CO2 Table을 출력할 수 있도록 설계했습니다.

#### 2. Pinia를 활용한 상태 관리

- Pinia는 Vue 3에서 권장되는 상태 관리 라이브러리로, 사용하기 쉬운 API와 Reactivity를 기반으로 효율적인 데이터 관리를 가능하게 합니다. 이 프로젝트에서는 사용자의 숨 참기 기록을 Pinia를 통해 관리했습니다.

## 🚀 주요 기능

- **맞춤형 CO2 Table**: 사용자가 자신의 숨 참기 최고 기록(초 단위)을 입력하면, 그에 기반하여 맞춤형 훈련 테이블이 자동으로 생성됩니다. 이 훈련 테이블은 숨을 참는 시간을 점진적으로 늘리면서 이산화탄소 내성을 높이는 데 도움을 줍니다.
- **쉬운 인터페이스**: 간단한 입력만으로 CO2 Table을 빠르게 생성할 수 있어, 사용자는 복잡한 설정 없이도 훈련을 바로 시작할 수 있습니다.
