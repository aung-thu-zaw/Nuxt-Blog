<script setup>
defineProps({ blog: Object, comment: Object });

const isReplyBoxOpened = ref(false);
</script>

<template>
  <div class="p-4">
    <div class="flex items-center justify-between">
      <div class="flex items-center">
        <img
          :src="comment.user?.avatar"
          :alt="comment.user?.avatar"
          class="w-10 h-10 object-cover rounded-full mr-2 border border-slate-300 ring-2 ring-slate-200"
        />

        <div class="flex flex-col items-start">
          <h3 class="font-bold text-slate-700">{{ comment.user?.name }}</h3>
        </div>
      </div>

      <p class="text-slate-600 text-sm font-medium">
        {{ comment?.created_at }}
      </p>
    </div>

    <div class="pl-12">
      <p class="text-sm text-slate-700 font-medium">
        {{ comment?.comment }}
      </p>
    </div>

    <div class="flex items-center justify-end mt-3">
      <button
        v-if="!isReplyBoxOpened"
        @click="isReplyBoxOpened = !isReplyBoxOpened"
        class="font-medium text-xs text-slate-600 hover:text-slate-800"
      >
        <i class="fa-solid fa-comment-dots"></i>
        Reply
      </button>
      <button
        v-else
        @click="isReplyBoxOpened = false"
        class="font-medium text-xs text-red-600 hover:text-red-500"
      >
        <i class="fa-solid fa-circle-xmark"></i>

        Cancel
      </button>
    </div>

    <!-- Reply Form -->
    <!-- <div v-show="isReplyBoxOpened">
      <BlogReplyForm :blog="blog" :comment="comment" @updateReplyBox="isReplyBoxOpened = false" />
    </div> -->
  </div>
</template>
