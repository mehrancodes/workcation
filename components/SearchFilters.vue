<template lang="pug">
  section(class='bg-gray-800 xl:w-72')
    div(class='flex justify-between px-4 py-2 xl:hidden')
      div.relative.w-full.max-w-xs
        div.flex.items-center.absolute.inset-y-0.left-0.pl-3
          svg.h-6.w-6.fill-current.text-gray-600(width='24' height='24' xmlns='http://www.w3.org/2000/svg')
            path(fill-rule='evenodd' clip-rule='evenodd' d='M16.32 14.906l1.096 1.096c.412-.022.83.123 1.145.437l3 3a1.5 1.5 0 0 1-2.122 2.122l-3-3a1.497 1.497 0 0 1-.437-1.145l-1.096-1.096a8 8 0 1 1 1.414-1.414zM10 16a6 6 0 1 0 0-12 6 6 0 0 0 0 12z')
        input(placeholder='Search By Keywords' class='block w-full bg-gray-900 text-white rounded-lg pl-10 pr-4 py-2 focus:outline-none focus:bg-white focus:text-gray-900')

      button(
        :class="{ 'bg-gray-600': filtersOpen, 'bg-gray-700': !filtersOpen }"
        class='ml-4 inline-flex items-center text-white rounded-lg shadow pl-3 pr-4 hover:bg-gray-600 focus:outline-none focus:shadow-outline'
        @click='toggle'
      )
        svg.h-6.w-6.fill-current.text-gray-500(width='24' height='24' xmlns='http://www.w3.org/2000/svg')
          path(fill-rule='evenodd' clip-rule='evenodd' d='M3 6a1 1 0 0 1 1-1h16a1 1 0 1 1 0 2H4a1 1 0 0 1-1-1zm3 6a1 1 0 0 1 1-1h10a1 1 0 1 1 0 2H7a1 1 0 0 1-1-1zm4 5a1 1 0 1 0 0 2h4a1 1 0 1 0 0-2h-4z')

        span.ml-1.mt-1.font-medium Filters
    
    form(:class="{ 'hidden': !filtersOpen, 'block': filtersOpen }" class='xl:flex xl:flex-col xl:block xl:h-full xl:justify-between')
      div(class='lg:flex xl:block xl:overflow-y-auto')
        div(class='px-4 py-4 lg:w-1/3 lg:border-t lg:border-gray-900 xl:w-full xl:border-t-0')
          div(class='flex flex-wrap -mx-2')
            label(class='block px-2 w-1/2 sm:w-1/4 lg:w-1/2')
              span.text-sm.font-semibold.text-gray-500 Bedrooms
              select(class='mt-1 form-select block w-full text-white focus:bg-gray-600')
                option 4
            label(class='block px-2 w-1/2 sm:w-1/4 lg:w-1/2')
              span.text-sm.font-semibold.text-gray-500 Bathrooms
              select(class='mt-1 form-select block w-full text-white focus:bg-gray-600')
                option 2
            label(class='mt-4 block w-full px-2 sm:mt-0 sm:w-1/2 lg:w-full lg:mt-4')
              span.text-sm.font-semibold.text-gray-500 Price Range
              select(class='mt-1 form-select block w-full text-white focus:bg-gray-600')
                option Up to $2,000 /wk

        div(class='px-4 py-4 border-t border-gray-900 lg:w-1/4 lg:pb-10 xl:pb-6 lg:border-l xl:w-full')
          span(class='block text-sm font-semibold text-gray-500 lg:mt-1 lg:pl-2 xl:pl-0') Property Type
          
          div(class='sm:flex sm:-mx-2 lg:block lg:pl-2 xl:pl-0')
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-full lg:px-1 lg:mt-4')
              input(class='form-radio bg-gray-900 focus:bg-gray-700' type='radio' name='propertyType' value='house')
              span.ml-2.text-white House
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-full lg:px-1 lg:mt-4')
              input(class='form-radio bg-gray-900 focus:bg-gray-700' type='radio' name='propertyType' value='apartment')
              span.ml-2.text-white Apartment
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-full lg:px-1 lg:mt-4')
              input(class='form-radio bg-gray-900 focus:bg-gray-700' type='radio' name='propertyType' value='loft')
              span.ml-2.text-white Loft
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-full lg:px-1 lg:mt-4')
              input(class='form-radio bg-gray-900 focus:bg-gray-700' type='radio' name='propertyType' value='townhouse')
              span.ml-2.text-white Townhouse

        div(class='px-4 py-4 border-t border-gray-900 lg:w-1/2 lg:pb-10 xl:pb-6 lg:border-l xl:w-full')
          span(class='block mt-1 text-sm font-semibold text-gray-500 lg:mt-1 lg:pl-8 xl:pl-0') Amenities
          
          div(class='sm:flex sm:flex-wrap sm:-mx-2 lg:pl-8 xl:pl-0')
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-1/2 lg:mt-4 xl:w-full')
              input(class='form-checkbox bg-gray-900 focus:bg-gray-700' type='checkbox' name='balcony')
              span.ml-2.text-white Balcony
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-1/2 lg:mt-4 xl:w-full')
              input(class='form-checkbox bg-gray-900 focus:bg-gray-700' type='checkbox' name='airConditioning')
              span.ml-2.text-white Air Conditioning
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-1/2 lg:mt-4 xl:w-full')
              input(class='form-checkbox bg-gray-900 focus:bg-gray-700' type='checkbox' name='pool')
              span.ml-2.text-white Pool
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-1/2 lg:mt-4 xl:w-full')
              input(class='form-checkbox bg-gray-900 focus:bg-gray-700' type='checkbox' name='beach')
              span.ml-2.text-white Beach
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-1/2 lg:mt-4 xl:w-full')
              input(class='form-checkbox bg-gray-900 focus:bg-gray-700' type='checkbox' name='petFriendly')
              span.ml-2.text-white Pet Friendly
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-1/2 lg:mt-4 xl:w-full')
              input(class='form-checkbox bg-gray-900 focus:bg-gray-700' type='checkbox' name='kidFriendly')
              span.ml-2.text-white Kid Friendly
            label(class='flex items-center mt-3 sm:w-1/4 sm:px-2 lg:w-1/2 lg:mt-4 xl:w-full')
              input(class='form-checkbox bg-gray-900 focus:bg-gray-700' type='checkbox' name='parking')
              span.ml-2.text-white Parking
      div.bg-gray-900.px-4.py-4
        button(class='block w-full sm:w-auto bg-indigo-500 font-semibold text-white px-4 py-2 rounded-lg xl:block sm:w-full') Update results
</template>

<script>
export default {
  data: () => ({
    filtersOpen: true
  }),
  methods: {
    toggle() {
      this.filtersOpen = !this.filtersOpen
    }
  }
}
</script>
