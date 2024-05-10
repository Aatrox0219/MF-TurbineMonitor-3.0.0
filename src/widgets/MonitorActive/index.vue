<template>
  <WidgetPanel title="状态监测">
    <BaseTable :columns="columns" :data="dataSource"></BaseTable>
  </WidgetPanel>
</template>
<script setup lang="ts">
import BaseTable from '@/components/BaseTable/index.vue'
import { reactive } from 'vue'
import WidgetPanel from '../WidgetPanel.vue'

const columns = [
  {
    title: '部件名称',
    dataIndex: 'name',
    width: '25%',
  },
  {
    title: '监测时间',
    dataIndex: 'time',
    width: '55%',
  },
  {
    title: '状态',
    dataIndex: 'status',
    width: '20%',
  },
]
const dataSource = reactive([
  {
    name: 'L1电压',
    time: '2024/06/12 12:00',
    status: '正常',
  },
  {
    name: 'L2电压',
    time: '2024/06/12 12:00',
    status: '正常',
  },
  {
    name: 'L3电压',
    time: '2024/06/12 12:00',
    status: '正常',
  },
  {
    name: 'UPS电压',
    time: '2024/06/12 12:00',
    status: '正常',
  },
])
</script>
