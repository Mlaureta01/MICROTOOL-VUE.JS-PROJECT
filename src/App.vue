
<template>
  <header>
      <div class="align-items-center bg-light text-white mt-3 pb-4" style="border-bottom: 3px solid #adadad; background-color: #adadad !important;">
        <div class="p-4">
          <h5 class="text-dark text-center">Project in Advance Web Application</h5>
          <h1 class="text-warning text-center" style="font-size: 90px;">Microtool Project</h1>
        </div>
        <div class="container">
          <div class="row">
            <div class="col-md-6">
              <div class="card mt-3 w-100 mx-2 mb-3" :class="flexBox">
                <a @click="showFlexbox" class="text-decoration-none" >
                  <div class="card-body">
                    <h5 class="card-title">Flexbox</h5>
                    <p class="card-text">A CSS layout module.</p>
                  </div>
                </a>
              </div>
            </div>
            <div class="col-md-6">
              <div @click="showPasswordGenerator" class="card mt-3 w-100 mx-2 mb-3" :class="passGen">
                <a href="javascript: void(0)" class="text-decoration-none">
                  <div class="card-body">
                    <h5 class="card-title">Password Generator</h5>
                    <p class="card-text">A random password generator.</p>
                  </div>
                </a>
              </div>
            </div>
            <div class="col-md-6">
              <div @click="showCountdownTimer" class="card mt-3 w-100 mx-2 mb-3" :class="countTimer">
                <a href="javascript: void(0)" class="text-decoration-none">
                  <div class="card-body">
                    <h5 class="card-title">Countdown Timer</h5>
                    <p class="card-text">A simple countdown timer.</p>
                  </div>
                </a>
              </div>
            </div>
            <div class="col-md-6">
              <div @click="showMetricConverter" class="card mt-3 w-100 mx-2 mb-3" :class="metricCon">
                <a href="javascript: void(0)" class="text-decoration-none">
                  <div class="card-body">
                    <h5 class="card-title">Metric Converter</h5>
                    <p class="card-text">A conversion tool for metric units</p>
                  </div>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
  </header>
  <div class="container py-3" style="height: 100vh;">
    <div class="row">
      
      <Flexbox :showFlexboxComponent="showFlexboxComponent"/>
      <PasswordGenerator :showPasswordGeneratorComponent="showPasswordGeneratorComponent"/> 
      <CountdownTimer :showCountdownTimerComponent="showCountdownTimerComponent"/>
      <MetricConverter :showMetricConverterComponent="showMetricConverterComponent"/>
    </div>
  </div>
</template>

<script>
  import Flexbox from './components/Flexbox.vue'
  import PasswordGenerator from './components/PasswordGenerator.vue'
  import CountdownTimer from './components/CountdownTimer.vue'
  import MetricConverter from './components/MetricConverter.vue'

  export default{
    components: {Flexbox, CountdownTimer, MetricConverter, PasswordGenerator},
    data(){
      return{
        showMetricConverterComponent: false,
        showFlexboxComponent: true,
        showPasswordGeneratorComponent: false,
        showCountdownTimerComponent: false,
        flexBox: 'active',
        passGen: '',
        countTimer: '',
        metricCon: '',
      }
    },
    methods: {
      showFlexbox(){
        this.showFlexboxComponent = true
        this.showPasswordGeneratorComponent = false
        this.showCountdownTimerComponent = false
        this.showMetricConverterComponent = false
        this.flexBox = 'active'
        this.CurrencyCon = ''
        this.passGen = ''
        this.countTimer = ''
        this.metricCon = ''

      },
      showPasswordGenerator(){
        this.showFlexboxComponent = false
        this.showPasswordGeneratorComponent = true
        this.showCountdownTimerComponent = false
        this.showMetricConverterComponent = false
        this.flexBox = ''
        this.CurrencyCon = ''
        this.passGen = 'active'
        this.countTimer = ''
        this.metricCon = ''
      },
      showCountdownTimer(){
        this.showFlexboxComponent = false
        this.showPasswordGeneratorComponent = false
        this.showCountdownTimerComponent = true
        this.showMetricConverterComponent = false
        this.flexBox = ''
        this.CurrencyCon = ''
        this.passGen = ''
        this.countTimer = 'active'
        this.metricCon = ''
      },
      showMetricConverter(){
        this.showFlexboxComponent = false
        this.showPasswordGeneratorComponent = false
        this.showCountdownTimerComponent = false
        this.showMetricConverterComponent = true
        this.flexBox = ''
        this.CurrencyCon = ''
        this.passGen = ''
        this.countTimer = ''
        this.metricCon = 'active'
      }
    }
  }
</script>

<style>
  div .active{
    background-color: #3a4b58;
    cursor: pointer;
  }
  div .active a{
    color: aliceblue;
  }
  div a{
    color: #2c3f50;
  }
</style>