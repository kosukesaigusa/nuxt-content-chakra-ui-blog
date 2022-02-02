<template>
  <div class="container">
    <CThemeProvider>
      <CColorModeProvider>
        <CBox font-family="body" as="main">
          <Header />
          <CReset />
          <Nuxt />
        </CBox>
      </CColorModeProvider>
    </CThemeProvider>
  </div>
</template>
<script>
import {
  CThemeProvider,
  CColorModeProvider,
  CReset,
  CBox
} from '@chakra-ui/vue'
import Header from '~/components/header/Header.vue'

export default {
  name: 'DefaultLayout',
  components: {
    CThemeProvider,
    CColorModeProvider,
    CReset,
    CBox,
    Header
  }
}
</script>
