<template>
  <q-page class="flex flex-center">
    <q-virtual-scroll
      style="max-height: 300px;"
      :items="heavyList"
      separator
      v-slot="{ item, index }"
    >
      <q-intersection
        :key="index"
        transition="flip-right"
        class="example-item"
      >
        <q-item
          dense
        >
          <q-item-section>
            <q-item-label>
              #{{ index }} - {{ item.label }}
            </q-item-label>
          </q-item-section>
        </q-item>
      </q-intersection>
    </q-virtual-scroll>
  </q-page>
</template>

<script>
import {defineComponent} from 'vue'
const maxSize = 10000
const heavyList = []

for (let i = 0; i < maxSize; i++) {
  heavyList.push({
    label: 'Option ' + (i + 1)
  })
}
export default defineComponent({
  name: 'IndexPage',
  data() {
    return {
      heavyList
    }
  },
})
</script>
