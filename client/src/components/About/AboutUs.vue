<template>
  <div>
    <v-card
      :elevation="2"
      class="mx-auto"
      max-width="800"
    >
      <v-toolbar
        flat
        class="body-1 pt-2"
      >
        <v-toolbar-title>{{ $t('about.aboutUs.title') }}</v-toolbar-title>
        <v-divider class="mx-4" />
      </v-toolbar>

      <v-card-title>
        NETUNION
      </v-card-title>
      <v-card-subtitle>
        电子科技大学网络管理委员会
      </v-card-subtitle>
      <v-card-text class="body-1">
        <div>长期摸鱼，偶尔招新。</div>
        <div>联系我们：<a href="mailto:recruit@dormforce.net?body=MAIL FROM INTERNET REPAIR SYSTEM">recruit@dormforce.net</a></div>
      </v-card-text>

      <v-card-title>
        NETUNION DNRS WEB
      </v-card-title>
      <v-card-subtitle>
        电子科技大学宿舍网络在线报修平台
      </v-card-subtitle>
      <v-card-text class="body-1">
        <span>Patch Version:
          <span
            @click="toChangeLog"
            style="cursor: pointer;"
          >{{ version }}<v-icon small right>mdi-open-in-new</v-icon>
          </span>
        </span>
      </v-card-text>

      <v-card-actions>
        <v-btn
          class="ma-2"
          depressed
          href="https://github.com/uestclug/netunion-dnrs-web/issues"
          target="_blank"
        >
          <v-icon left>mdi-github</v-icon>
          {{ $t('about.aboutUs.issues') }}
        </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'AboutUs',
  data: () => ({
    version: process.env.VUE_APP_VERSION_CODE
  }),
  methods: {
    toChangeLog () {
      window.open('https://github.com/uestclug/netunion-dnrs-web/blob/master/CHANGELOG.md')
    }
  }
}
</script>
