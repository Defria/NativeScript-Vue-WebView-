<template>
  <Page class="page" actionBarHidden="true" backgroundSpanUnderStatusBar="true">
    <ActionBar title="Welcome to NativeScript-Vue!"/>
    <GridLayout columns="*" rows="*">
      <WebView ref="myWebView" :src="url" v-on:loaded="onPageLoaded()"/>
    </GridLayout>
  </Page>
</template>

<script >
export default {
  components: {},

  data() {
    return {
      url: "https://nativescripting.com/"
    };
  },
  mounted() {},
  methods: {
    onPageLoaded() {
      let webview = this.$refs.myWebView._nativeView;
      webview.on("loadStarted", args => {console.log("LOAD STARTED EVENT", args.url)});
      webview.on("loadFinished", args => {console.log("LOAD FINISHED EVENT", args.url)});
    }
  }
};
</script>
<style>
</style>
