<template lang="pug">
  div
    div(class='relative pb-5/6')
      img(
        class='absolute inset-0 h-full w-full rounded-lg shadow-md object-cover'
        :src='property.imageUrl'
      )
    div(class='relative px-4 -mt-16')
      div.bg-white.rounded-lg.px-4.py-3.shadow-lg
        div.flex
          span.inline-block.px-2.py-1.leading-none.bg-teal-200.text-teal-800.rounded-full.font-semibold.uppercase.tracking-wide.text-xs Plus
          div.ml-2.text-xs.text-gray-600.font-semibold.uppercase.tracking-wide
            | {{ property.beds }} {{ property.beds === 1 ? 'bed' : 'beds' }} &bull; {{ property.baths }} {{ property.baths === 1 ? 'bath' : 'baths' }}
        h4.text-gray-900.font-semibold.text-lg.mt-1 {{ property.title }}
        div.mt-1
          span.text-gray-900 {{ formattedPrice }}
          span.text-gray-600.ml-1.text-sm /wk
        div.flex.items-center.mt-2.text-sm.mt-2
          svg.fill-current(v-for="i in 5" :class="property.rating >= i ? 'text-teal-500' : 'text-gray-400'" width='14' height='14' fill='none' xmlns='http://www.w3.org/2000/svg')
            path(fill-rule='evenodd' clip-rule='evenodd' d='M4.283 11.93a1 1 0 0 1-1.451-1.054l.472-2.754-2-1.951a1 1 0 0 1 .553-1.706l2.766-.402L5.86 1.557a1 1 0 0 1 1.793 0L8.89 4.063l2.765.402a1 1 0 0 1 .555 1.706l-2.002 1.95.473 2.755A1 1 0 0 1 9.23 11.93l-2.474-1.3-2.473 1.3z')
          span.ml-2 {{ property.reviewCount }} reviews
</template>

<script>
export default {
  props: {
    property: {
      required: true,
      type: Object
    }
  },
  computed: {
    formattedPrice() {
      const formatter = new Intl.NumberFormat('en-US', {
        style: 'currency',
        currency: 'USD'
      })
      return formatter.format(this.property.price / 100)
    }
  }
}
</script>
