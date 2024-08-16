<template>
  <q-page class="q-pa-lg">
    <div class="row">
      <div class="col-12">
        <h2 class="text-h6">CO2 Table이란?</h2>
        <p class="text-body1">
          이산화탄소(CO2) 내성을 높이는 데 사용되는 훈련 방법 중 하나로,
          프리다이빙에서 CO2 Table 훈련은 다이빙 중 몸이 CO2 축적에 더 잘 견딜
          수 있도록 하기 위해 설계된 표준화된 호흡 훈련입니다.<br />이 훈련은
          일반적으로 일정 시간 동안 숨을 참는 동안 점차적으로 호흡 주기를 줄이는
          방식으로 진행됩니다.
        </p>

        <h2 class="text-h6">CO2 Table 훈련 순서</h2>
        <div class="text-body1">
          <ol>
            <li>
              준비 호흡: 편안한 자세를 취한 뒤, 진정될 때까지 1(들숨):2(날숨)의
              비율로 복식 호흡을 합니다. 보통 2-3분 정도 진행합니다.
            </li>
            <li>
              숨 참기: 숨을 깊게 들이쉰 후, 사전에 정해진 시간 동안 숨을
              참습니다. 초보자는 자신의 최고 기록의 절반에서 시작하는 것이
              좋습니다.
            </li>
            <li>
              회복 호흡: 호흡이 돌아올 때 까지 숨을 머금고 있다가 뱉어줍니다.
              (보통 3~4회)
            </li>
            <li>
              휴식 간격: 이후 회복 호흡 시간(휴식 간격)을 이전 회차보다 15초씩
              줄여가며 총 6회에서 8회 정도 연습합니다.
            </li>
          </ol>
        </div>
      </div>
      <div class="col-12 col-md-6">
        <h3 class="text-h6">맞춤형 CO2 Table 만들기</h3>
        <RecordForm></RecordForm>
        <Co2Table :rows :columns></Co2Table>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import Co2Table from 'src/components/Co2Table.vue';
import RecordForm from 'src/components/RecordForm.vue';
import { useRecordStore } from 'src/stores/record';
import { computed, ref } from 'vue';

const store = useRecordStore();
const count = ref(8);
const rows = computed(() => {
  const data = [];
  for (let i = 0; i < count.value; i++) {
    data.push({
      count: i + 1,
      hold: store.record / 2 || 60,
      rest: 120 - i * 15,
    });
  }

  return data;
});
const columns = [
  {
    name: 'name',
    label: '횟수',
    align: 'center',
    field: row => row.count,
    format: val => `${val}회`,
  },
  {
    name: '숨 참기',
    align: 'center',
    label: '숨 참기',
    field: row => row.hold,
    format: val => `${val}초`,
  },
  {
    name: '휴식',
    align: 'center',
    label: '휴식',
    field: row => row.rest,
    format: val => `${val}초`,
  },
];
</script>
