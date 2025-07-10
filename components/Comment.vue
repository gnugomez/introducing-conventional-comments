<script setup lang="ts">

defineProps({
  username: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: false,
  },
  role: {
    type: String,
    required: false,
  },
  timeAgo: {
    type: String,
    required: false,
    default: "2 days ago"
  },
})

</script>
<template>

  <div class="flex space-x-3">
    <!-- Avatar -->
    <div class="w-8 h-8 bg-orange-400 rounded-full flex-shrink-0 flex items-center justify-center">
    </div>

    <!-- Content -->
    <div class="flex-1 min-w-0 p-2 bg-gray-800 border-px border-gray-700 rounded-md">
      <!-- Header -->
      <div class="flex items-center gap-2 mb-1">
        <span class="text-sm font-medium">{{ name || username }}</span>
        <span class="text-sm text-gray-500">@{{ username }}</span>
        <span class="text-sm text-gray-400">•</span>
        <span class="text-sm text-gray-500">{{ timeAgo }}</span>

        <!-- Role badges -->
        <div class="flex gap-1 ml-auto">
          <span v-if="role" class="px-2 py-1 text-xs font-medium text-blue-700 bg-blue-100 rounded-full">
            {{ role }}
          </span>
          <div class="flex gap-1">
            <!-- Action buttons -->
            <button class="p-1 text-gray-400 hover:text-gray-600 rounded w-6 h-6 flex items-center justify-center">
              <heroicons-share />
            </button>
            <button class="p-1 text-gray-400 hover:text-gray-600 rounded w-6 h-6 flex items-center justify-center">
              <heroicons-arrow-uturn-left />
            </button>
            <button class="p-1 text-gray-400 hover:text-gray-600 rounded w-6 h-6 flex items-center justify-center">
              <heroicons-ellipsis-horizontal />
            </button>
          </div>
        </div>
      </div>

      <!-- Comment content -->
      <div class="text-sm comment-content">
        <slot name="comment"></slot>
      </div>
    </div>
  </div>

</template>

<style scoped>
.comment-content :deep(p):first-child {
  margin-top: 0;
}
.comment-content :deep(p):last-child {
  margin-bottom: 0;
}

/* Hover effects */
button:hover {
  background-color: #f3f4f6;
}
</style>