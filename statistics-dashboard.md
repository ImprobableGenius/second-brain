---
title: "Statistics Dashboard"
---

- Last updated: `2026-04-07`
- Source: [[statistics|Productivity Statistics]]

## Weighted Output Vs Baseline

```mermaid
xychart-beta
    title "Weighted Output vs Rolling Baseline"
    x-axis ["03-17","03-18","03-19","03-20","03-23","03-24","03-25","03-26","03-27","03-30","03-31","04-01","04-02","04-06"]
    y-axis "Hours" 0 --> 14
    bar [4.0,13.8,8.4,8.2,6.7,13.2,4.5,6.9,5.0,2.4,6.4,13.0,5.2,5.1]
    line [4.0,4.0,8.9,8.4,8.3,8.2,8.4,8.2,6.9,6.7,5.0,5.0,6.4,5.2]
```

## Work Mix

```mermaid
xychart-beta
    title "Shipped vs Response vs Progress"
    x-axis ["03-17","03-18","03-19","03-20","03-23","03-24","03-25","03-26","03-27","03-30","03-31","04-01","04-02","04-06"]
    y-axis "Hours" 0 --> 14
    bar [4.0,11.0,7.0,7.0,6.0,10.5,2.0,2.0,5.0,0.0,5.0,13.0,1.0,0.0]
    bar [0.0,4.0,2.0,1.0,1.0,1.0,3.5,7.0,0.0,2.0,2.0,0.0,6.0,3.0]
    bar [0.0,0.0,0.0,1.0,0.0,4.0,0.0,0.0,0.0,2.0,0.0,0.0,0.0,6.0]
```

## Scope Pressure

```mermaid
xychart-beta
    title "New Scope and Scope Pressure"
    x-axis ["03-17","03-18","03-19","03-20","03-23","03-24","03-25","03-26","03-27","03-30","03-31","04-01","04-02","04-06"]
    y-axis "Percent / Hours" 0 --> 900
    bar [0,26,6,10,59,8,7,1,0,0,0,0,32,2]
    line [0,188,71,122,881,61,157,14,0,0,0,0,615,39]
```

## Adaptive Productivity Index

```mermaid
xychart-beta
    title "Adaptive Productivity Index (API)"
    x-axis ["03-17","03-18","03-19","03-20","03-23","03-24","03-25","03-26","03-27","03-30","03-31","04-01","04-02","04-06"]
    y-axis "API" 0 --> 360
    bar [100,345,94,98,81,161,53,84,72,36,128,260,81,98]
```

## Blockers

```mermaid
xychart-beta
    title "Blocked Hours"
    x-axis ["03-17","03-18","03-19","03-20","03-23","03-24","03-25","03-26","03-27","03-30","03-31","04-01","04-02","04-06"]
    y-axis "Hours" 0 --> 7
    bar [0.0,0.0,0.0,1.0,0.0,1.0,6.0,5.0,5.0,0.0,0.0,0.0,0.0,0.0]
```

## Read

- The strongest delivery spikes so far are `2026-03-18`, `2026-03-24`, and `2026-04-01`.
- The biggest scope-pressure spikes are `2026-03-23` and `2026-04-02`, both driven by major intake/bundle creation rather than weak execution alone.
- The lowest-output days are not pure failure days; they are mostly response-heavy or blocker-heavy days.
- The rolling baseline is now stable enough to make the API useful as a short-horizon management signal, but it is still not strong enough for long-range forecasting by itself.
