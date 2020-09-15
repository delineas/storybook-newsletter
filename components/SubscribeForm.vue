<template>
  <div
    class="w-full border-b flex flex-row flex-wrap items-center justify-center p-1 text-gray-100 bg-gray-800"
  >
    <div class="flex justify-center mt-6">
      <div class="bg-white rounded-lg">
        <div class="flex flex-wrap justify-between md:flex-row">
          <input
            type="email"
            placeholder="Tu email"
            name="email"
            required=""
            class="m-1 p-2 appearance-none text-gray-700 text-sm focus:outline-none"
          />
          <button
            type="submit"
            class="w-full m-1 p-2 text-sm bg-gray-800 rounded-lg font-semibold uppercase lg:w-auto"
          >
            <slot />
          </button>
        </div>
      </div>
      <div aria-hidden="true" style="position:absolute;left:-5000px">
        <input name="a_password" tabindex="-1" autocomplete="off" />
      </div>
      <div class="flex flex-col pt-4">
        <label class="flex justify-start items-start py-1 text-sm"
          ><input
            type="checkbox"
            name="gdpr"
            value="1"
            required=""
            class="h-3 w-3 mr-1 mt-1"
          />
          He leído y acepto la&nbsp;<a
            :href="url"
            target="_blank"
            class="underline"
            >política de privacidad</a
          >.</label
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    url: {
      type: String,
      default: '/privacidad'
    },
    service: {
        type: String,
        default: 'mailchimp'
    }
  },
  computed: {
      isSendfox() {
          return this.service === 'sendfox'
      }
  }
};
</script>
