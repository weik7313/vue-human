<template>
  <transition name="has-slide">
    <mn-rows>
      <mn-row fixed visible>
        <demo-filter-bar></demo-filter-bar>
      </mn-row>
      <mn-row>
        <mn-scroller>
          <mn-section>
            <mn-letter>
              <h1>Sign Up</h1>
              <small>form and validate</small>
            </mn-letter>

            <mn-cols>
              <mn-col query="sm-6">
                <demo-form></demo-form>
              </mn-col>
            </mn-cols>
          </mn-section>
        </mn-scroller>
      </mn-row>
    </mn-rows>
  </transition>
</template>

<script>
  import FormRadio from './radio'
  import FormCheckbox from './checkbox'
  import FormBasic from './basic'
  import FormDate from './date'
  import FormSwitch from './switch'
  import FormSelect from './select'
  import FormCounter from './counter'
  import DemoFilterBar from '../filter-bar'
  import DemoForm from './form'

  export default {
    components: {
      FormRadio,
      FormCheckbox,
      FormBasic,
      FormDate,
      FormSwitch,
      FormSelect,
      FormCounter,
      DemoFilterBar,
      DemoForm
    }
  }
</script>
