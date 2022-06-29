<template>
  <div>
    <div class="mb-4">
      <Link class="group flex items-center py-3" href="/">
        <icon name="dashboard" class="mr-2 w-4 h-4" :class="isUrl('') ? 'fill-impii' : 'fill-white group-hover:fill-impii'" />
        <div :class="isUrl('') ? 'text-impii' : 'text-white group-hover:text-impii'">Dashboard</div>
      </Link>
    </div>
    <div class="mb-4">
      <Link class="group flex items-center py-3" href="/organizations">
        <icon name="office" class="mr-2 w-4 h-4" :class="isUrl('organizations') ? 'fill-impii' : 'fill-white group-hover:fill-impii'" />
        <div :class="isUrl('organizations') ? 'text-impii' : 'text-white group-hover:text-impii'">Organizations</div>
      </Link>
    </div>
    <div class="mb-4">
      <Link class="group flex items-center py-3" href="/contacts">
        <icon name="users" class="mr-2 w-4 h-4" :class="isUrl('contacts') ? 'fill-impii' : 'fill-white group-hover:fill-impii'" />
        <div :class="isUrl('contacts') ? 'text-impii' : 'text-white group-hover:text-impii'">Contacts</div>
      </Link>
    </div>
    <div class="mb-4">
      <Link class="group flex items-center py-3" href="/reports">
        <icon name="printer" class="mr-2 w-4 h-4" :class="isUrl('reports') ? 'fill-impii' : 'fill-white group-hover:fill-impii'" />
        <div :class="isUrl('reports') ? 'text-impii' : 'text-white group-hover:text-impii'">Reports</div>
      </Link>
    </div>
  </div>
</template>

<script>
import { Link } from '@inertiajs/inertia-vue3'
import Icon from '@/Shared/Icon'

export default {
  components: {
    Icon,
    Link,
  },
  methods: {
    isUrl(...urls) {
      let currentUrl = this.$page.url.substr(1)
      if (urls[0] === '') {
        return currentUrl === ''
      }
      return urls.filter((url) => currentUrl.startsWith(url)).length
    },
  },
}
</script>
