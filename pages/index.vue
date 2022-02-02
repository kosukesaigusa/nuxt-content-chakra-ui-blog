<template>
  <div class="container">
    <CBox
      v-bind="mainStyles[colorMode]"
      d="flex"
      max-w="100vw"
      flex-dir="column"
    >
      <CBox px="6">
        <CBox max-w="960px" mx="auto">
          <CFlex justify-content="left" w="100%">
            <CText mr="6" font-size="lg" font-weight="semibold" pb="3" border-bottom="2px">
              Trending
            </CText>
            <CText mr="6" font-size="lg" font-weight="semibold" pb="3">
              Following
            </CText>
            <CText mr="6" font-size="lg" font-weight="semibold" pb="3">
              Explore
            </CText>
          </CFlex>
        </CBox>
      </CBox>
      <CBox bg="#E6F2FF" px="6" py="12">
        <CBox max-w="960px" mx="auto">
          <CHeading as="h3" font-size="3xl" mb="8">
            Tech
          </CHeading>
          <CBox my="3">
            <CGrid template-columns="repeat(2, 1fr)" gap="6">
              <CFlex v-for="i in Array.from(Array(20).keys())" :key="i" w="100%">
                <CBox
                  w="92px"
                  h="92px"
                  bg="white"
                  p="4"
                  mr="4"
                  rounded="lg"
                  align="center"
                >
                  <CBox as="span" font-size="4xl">
                    🚀
                  </CBox>
                </CBox>
                <CBox flex-grow="1">
                  <CHeading as="h3" font-size="md" pb="2">
                    Firestore Security Rules の書き方と守るべき原則
                  </CHeading>
                  <CFlex>
                    <CBox mr="2">
                      <CImage
                        border-radius="full"
                        box-size="36px"
                        src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/93997/profile-images/1614305949"
                        alt="Kosuke Saigusa"
                      />
                    </CBox>
                    <CFlex flex-dir="column">
                      <CText font-size="sm" color="#6E7B85">
                        Kosuke Saigusa
                      </CText>
                      <CFlex>
                        <CText font-size="xs" color="#6E7B85" mr="2">
                          3日前
                        </CText>
                        <CText font-size="xs" color="#6E7B85" mr="2">
                          14 min read
                        </CText>
                        <CText font-size="xs" color="#6E7B85">
                          53 Likes
                        </CText>
                      </CFlex>
                    </CFlex>
                  </CFlex>
                </CBox>
              </CFlex>
            </CGrid>
          </CBox>
        </CBox>
      </CBox>
    </CBox>
  </div>
</template>

<script lang="js">
import {
  CBox
} from '@chakra-ui/vue'

export default {
  name: 'IndexPage',
  components: {
    CBox
  },
  inject: ['$chakraColorMode', '$toggleColorMode'],
  data () {
    return {
      showModal: false,
      mainStyles: {
        dark: {
          bg: 'gray.700',
          color: 'whiteAlpha.900'
        },
        light: {
          bg: 'white',
          color: 'gray.900'
        }
      }
    }
  },
  computed: {
    colorMode () {
      return this.$chakraColorMode()
    },
    theme () {
      return this.$chakraTheme()
    },
    toggleColorMode () {
      return this.$toggleColorMode
    }
  },
  methods: {
    showToast () {
      this.$toast({
        title: 'Account created.',
        description: "We've created your account for you.",
        status: 'success',
        duration: 10000,
        isClosable: true
      })
    }
  }
}
</script>
