# react-native-pedometer-ios

React Native pedometer >=0.60 updated for pod support. The module is CMPedometer wrapper. More info about CMPedometer can be found in https://developer.apple.com/library/ios/documentation/CoreMotion/Reference/CMPedometer_class/

## Getting started

`$ npm install react-native-pedometer-ios --save`

### Mostly automatic installation

`$ react-native link react-native-pedometer-ios`

## Usage
```javascript
import PedometerIos from 'react-native-pedometer-ios';

// TODO: What to do with the module?
// start tracking from current time
var now = new Date()
PedometerIos.startPedometerUpdatesFromDate(now.getTime())

// query pedometer data from selected date to other selected date
const startDate = new Date(2019)
startDate.setHours(0,0,0,0)
const endDate = new Date()
PedometerIos.queryPedometerDataBetweenDates(startDate.getTime(), endDate.getTime(), (error, pedometerData) => {
  // do something with pedometer data
})

// determine pedometer availability
PedometerIos.isStepCountingAvailable(function(error, isAvailable) {
// do something
})

PedometerIos.isDistanceAvailable(function(error, isAvailable) {
// do something
})

PedometerIos.isFloorCountingAvailable(function(error, isAvailable) {
// do something
})

PedometerIos.isPaceAvailable(function(error, isAvailable) {
// do something
})

PedometerIos.isCadenceAvailable(function(error, isAvailable) {
// do something
})

PedometerIos.isPedometerEventTrackingAvailable(function(error, isAvailable) {
// do something
});

PedometerIos.authorizationStatus(function(error, status) {
// do something
/*
  Possible status values:
  -- 
  - "denied"
  - "authorized"
  - "restricted"
  - "not_determined"
  - "not_available" (on iOS < 11.0)
 */
});

// stop pedometer updates
PedometerIos.stopPedometerUpdates()
```
