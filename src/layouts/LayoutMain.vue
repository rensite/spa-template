<template lang='pug'>
.h-screen
  header.fixed.top-0.h-16.w-full
    .flex.items-center.justify-between.h-full.px-6
      div.grid.grid-flow-col.gap-1.text-slate-400.text-sm.sm_text-lg.text-right
        strong.text-slate-600.font-bold {{ projectName }}
        span /
        span {{ projectSlogan }}
      a(v-show='githubLink.length' :href='githubLink' target='_blank').w-5.h-5
        IconGithub.text-slate-600.w-full.h-full

  .h-full.flex.flex-col.justify-center
    slot

  footer.fixed.bottom-0.h-10.w-full
    .h-full.pl-5.text-center.sm_text-right.sm_px-6
      span.text-slate-300.text-xs.sm_text-sm
        | &copy; <a :href='copyrightLink' class="underline uppercase" target='_blank'>{{ author }}</a> {{ year }}
</template>

<script setup>
  import IconGithub from '@/components/icons/Github.vue';

  defineProps({
    projectName: String,
    projectSlogan: String,
    githubLink: String,
    copyrightLink: String,
    author: String,
    year: String,
  });
</script>