<template>
  <v-container>
    <app-first-image :title="`Post ${pageId}`"/>
    <p class="mt-4 mb-4 text-justify">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas cupiditate amet, accusamus fugit libero rem corrupti animi consequatur ipsum, explicabo excepturi suscipit? Reprehenderit iusto necessitatibus impedit. Fugit eaque beatae reprehenderit?
    Impedit assumenda suscipit officia accusantium adipisci quidem autem a qui accusamus, dolore laborum dicta ipsa fuga facere voluptates quibusdam provident totam, similique molestias corporis eius optio fugiat cupiditate. Corporis, dolore.
    Optio dolores eos voluptatum perferendis veniam minus amet labore eum minima? Possimus fugit nulla numquam? Perferendis nihil delectus eaque? Soluta facere autem nisi, cupiditate repudiandae fugiat consectetur ullam modi fugit.
    Incidunt cumque quibusdam quis aliquam. Ex deserunt cum nam maxime magnam. Ut iusto, debitis labore nemo, illum eaque, porro distinctio recusandae magnam deleniti aliquam eum impedit consequatur perspiciatis harum exercitationem.
    At minus officiis ut natus labore aspernatur neque quam repudiandae dolore architecto esse tempora dicta assumenda et nemo voluptatibus ipsam quasi praesentium, delectus necessitatibus? Accusantium doloremque similique minus optio magnam.
    Accusamus laudantium iure id, voluptate, illum laboriosam laborum iusto necessitatibus voluptatum optio aperiam perspiciatis! Sunt, odio! Eos blanditiis, quidem excepturi vero asperiores voluptatum accusantium assumenda iusto perferendis ea cupiditate amet.</p>
    <h3>Subtitle of post {{pageId}}</h3>
     <p class="mt-4 mb-4 text-justify">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas cupiditate amet, accusamus fugit libero rem corrupti animi consequatur ipsum, explicabo excepturi suscipit? Reprehenderit iusto necessitatibus impedit. Fugit eaque beatae reprehenderit?
    Impedit assumenda suscipit officia accusantium adipisci quidem autem a qui accusamus, dolore laborum dicta ipsa fuga facere voluptates quibusdam provident totam, similique molestias corporis eius optio fugiat cupiditate. Corporis, dolore.
    Optio dolores eos voluptatum perferendis veniam minus amet labore eum minima? Possimus fugit nulla numquam? Perferendis nihil delectus eaque? Soluta facere autem nisi, cupiditate repudiandae fugiat consectetur ullam modi fugit.
    Incidunt cumque quibusdam quis aliquam. Ex deserunt cum nam maxime magnam. Ut iusto, debitis labore nemo, illum eaque, porro distinctio recusandae magnam deleniti aliquam eum impedit consequatur perspiciatis harum exercitationem.
    At minus officiis ut natus labore aspernatur neque quam repudiandae dolore architecto esse tempora dicta assumenda et nemo voluptatibus ipsam quasi praesentium, delectus necessitatibus? Accusantium doloremque similique minus optio magnam.
    Accusamus laudantium iure id, voluptate, illum laboriosam laborum iusto necessitatibus voluptatum optio aperiam perspiciatis! Sunt, odio! Eos blanditiis, quidem excepturi vero asperiores voluptatum accusantium assumenda iusto perferendis ea cupiditate amet.</p>
    <app-comments />
  </v-container>
</template>

<script>
import firstImage from '@/components/coursePage/firstImage.vue'
import Comments from '@/components/Comments/commentForm.vue'
export default {
  validate ({ params }) {
    return /^\d+$/.test(params.id)
  },
  components: {
    'app-first-image': firstImage,
    'app-comments': Comments
  },
  asyncData ({ params }) {
    return {
      pageId: params.id
    }
  }
}
</script>
