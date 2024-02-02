<template>
    <ejs-bulletchart :dataSource="data" :valueField="valueField" :tooltip="tooltipSettings" :targetField="targetField" :height="height" :width="width"
        :title="title" :subtitle="subtitle" :minimum="minimum" :maximum="maximum" :interval="interval" categoryField="name" :minorTickLines="minorTickLine" :majorTickLines="majorTickLine"
        :legendSettings="legend" :valueFill="valueFill" :targetColor="targetColor" :animation="animation">
        <e-bullet-range-collection>
          <e-bullet-range end="25" opacity="1" color="#DBE7F3" name="poor"></e-bullet-range>
          <e-bullet-range end="37" opacity="1" color="#BBCEE7" name="avg"></e-bullet-range>
          <e-bullet-range end="45" opacity="1" color="#96B2D7" name="good"></e-bullet-range>
        </e-bullet-range-collection>
    </ejs-bulletchart>
</template>

<script setup>
import { provide } from 'vue';
import { BulletChartComponent as EjsBulletchart, BulletTooltip, BulletRangeCollectionDirective as EBulletRangeCollection, BulletRangeDirective as EBulletRange, BulletChartLegend } from "@syncfusion/ej2-vue-charts";

const data = [
    {
        requiredStories: 20,
        completedStories: 25,
        name: 'David',
        color: "#7f84e8"
    },
    {
        requiredStories: 25,
        completedStories: 20,
        name: 'Asif',
        color: "#dd8abd"
    },
    {
        requiredStories: 15,
        completedStories: 10,
        name: 'Thomas',
        color: "#70ad47"
    },
    {
        requiredStories: 40,
        completedStories: 39,
        name: 'Rohit',
        color: "#f8b883"
    },
    {
        requiredStories: 35,
        completedStories: 40,
        name: 'Virat',
        color: "#e56590"
    },
    {
        requiredStories: 28,
        completedStories: 25,
        name: 'Jude',
        color: "#357cd2"
    },
    {
        requiredStories: 10,
        completedStories: 18,
        name: 'Warner',
        color: "#404041"
    },
    {
        requiredStories: 30,
        completedStories: 28,
        name: 'Malik',
        color: "#00bdae"
    }
];
const minimum = 5;
const maximum = 45;
const interval = 5;
const tooltipSettings = { enable: true };
const title = 'Sprint planning';
const subtitle = 'Estimated in story points';
const height = '600px';
const width = '800px';
const minorTickLine = { width: 0 };
const majorTickLine = { color: 'teal' };
const legend = { visible: true };
const animation = { enable: true };
const valueFill = 'color';
const targetColor = '#304560';
const targetField = 'requiredStories';
const valueField = 'completedStories';
const bulletChart = [ BulletTooltip, BulletChartLegend ];
provide('bulletChart', bulletChart);
</script>