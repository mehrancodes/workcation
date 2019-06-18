<template lang="pug">
  div(class='min-h-screen bg-gray-200 antialiased min-h-screen xl:flex xl:flex-col xl:h-screen')
    wc-header(class='xl:flex-shrink-0')
    div(class='xl:flex xl:flex-1 xl:overflow-y-hidden')
      wc-search-filters

      main(class='py-6 xl:flex-1 xl:overflow-x-hidden')
        nuxt
</template>

<script>
import WcHeader from '@/components/Header'
import WcSearchFilters from '@/components/SearchFilters'

export default {
  components: {
    WcHeader,
    WcSearchFilters
  }
}
</script>
