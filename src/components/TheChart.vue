<template>
    <ejs-bulletchart :dataSource="data" :valueField="valueField" :tooltip="tooltip" :targetField="targetField" :height="height"
        :title="title" :minimum="minimum" :maximum="maximum" :interval="interval">
        <e-bullet-range-collection>
          <e-bullet-range end="100" color="red"></e-bullet-range>
          <e-bullet-range end="200" color="blue"></e-bullet-range>
          <e-bullet-range end="300" color="green"></e-bullet-range>
        </e-bullet-range-collection>
    </ejs-bulletchart>
</template>

<script setup>
import { provide } from 'vue';
import { BulletChartComponent as EjsBulletchart, BulletTooltip, BulletRangeCollectionDirective as EBulletRangeCollection, BulletRangeDirective as EBulletRange } from "@syncfusion/ej2-vue-charts";

const data = [
    { value: 100, target: 80 },
    { value: 200, target: 180 },
    { value: 300, target: 280 },
    { value: 400, target: 180 },
    { value: 500, target: 230 }
];
const minimum = 0;
const maximum = 300;
const interval = 50;
const tooltip = { enable: true };
const title = 'Revenue';
const height = '300px';
const targetField = 'target';
const valueField = 'value';
const bulletChart = [ BulletTooltip ];
provide('bulletChart', bulletChart);
</script>