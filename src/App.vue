<template>
  <q-layout view="hHh Lpr lFf" class="shadow-2 rounded-borders">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="fas fa-bars"
        />

        <q-toolbar-title>
          Startup Check List
        </q-toolbar-title>

        <!-- <div>Quasar v{{ $q.version }}</div> -->
        <q-btn
          flat
          dense
          round
          @click="changeLocale"
          aria-label="Language"
          icon="fas fa-language"
          class="language"
        />
      </q-toolbar>
    </q-header>
  <!-- bordered -->
  <q-drawer
        v-model="leftDrawerOpen"    
        :breakpoint="500"
        show-if-above>
        <q-scroll-area class="fit">
          <q-list padding class="menu-list">
            <q-item clickable tag="a" target="_blank" href="https://www.defmacro.org/2019/03/26/startup-checklist.html">
              <q-item-section avatar>
                <q-icon name="far fa-newspaper" />
              </q-item-section>

              <q-item-section>
                <q-item-label>{{$t('nav.reference')}}</q-item-label>
                <q-item-label caption>{{$t('thanks')}} Slava Akhmechet</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable tag="a" target="_blank" href="https://github.com/skys215/startup-checklist">
              <q-item-section avatar>
                <q-icon name="fas fa-code" />
              </q-item-section>
              <q-item-section>
                <q-item-label>{{$t('nav.github')}}</q-item-label>
                <q-item-label caption>https://github.com/skys215/startup-checklist</q-item-label>
              </q-item-section>
            </q-item>

            <q-separator />

            <q-item clickable tag="a" target="_blank" href="https://github.com/le0zh0u">
              <q-item-section avatar>
                <q-icon name="fas fa-language" />
              </q-item-section>

              <q-item-section>
                <q-item-label>由LeoZhou翻译</q-item-label>
                <q-item-label caption>https://github.com/le0zh0u</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable tag="a" target="_blank" href="https://blog.skys215.com/">
              <q-item-section avatar>
                <q-icon name="fas fa-blog" />
              </q-item-section>

              <q-item-section>
                <q-item-label>{{$t('nav.blog')}}</q-item-label>
                <q-item-label caption>https://blog.skys215.com/</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable tag="a" target="_blank" href="https://regexr-cn.com/">
              <q-item-section avatar>
                <q-icon name="fas fa-registered" />
              </q-item-section>

              <q-item-section>
                <q-item-label>{{$t('nav.regexr-cn')}}</q-item-label>
                <q-item-label caption>https://regexr-cn.com/</q-item-label>
              </q-item-section>
            </q-item>

          </q-list>
        </q-scroll-area>
      </q-drawer>
    <q-page-container>
      <HelloWorld class="bg-grey-2"/>
    </q-page-container>
  </q-layout>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { switchLang }  from '@/i18n'

export default {
  name: 'LayoutDefault',

  components: {
    HelloWorld
  },

  data () {
    return {
      leftDrawerOpen: this.$q.platform.is.desktop
    }
  },
  methods: {
    changeLocale() {
      switchLang()
    }
  }
}
</script>

<style lang="stylus" scoped>
.menu-list .q-item
  border-radius 0 32px 32px 0

.language
  margin-right: 1rem
</style>
