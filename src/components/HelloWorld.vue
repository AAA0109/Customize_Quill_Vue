<template>
  <div>
    <div class="d-flex align-items-center">
      <div class="mr-3">
        <img src="../assets/logo.svg" height="100" width="100" />
      </div>
      <div class="text-left">
        <h1 class="mb-0 mt-0">User1</h1>
        <p class="mb-0 mt-0">
          In publishing and graphic design, Lorem ipsum is a placeholder text
          commonly used to demonstrate the visual form of a document or a
          typeface without relying on meaningful content. Lorem ipsum may be
          used as a placeholder before final copy is available
        </p>
      </div>
    </div>
    <div class="d-flex align-items-center">
      <div class="mr-3">
        <img src="../assets/logo1.png" height="100" width="100" />
      </div>
      <div class="text-left">
        <h1 class="mb-0 mt-0">User2</h1>
        <p class="mb-0 mt-0">
          In publishing and graphic design, Lorem ipsum is a placeholder text
          commonly used to demonstrate the visual form of a document or a
          typeface without relying on meaningful content. Lorem ipsum may be
          used as a placeholder before final copy is available
        </p>
      </div>
    </div>
    <div class="d-flex align-items-center">
      <div class="mr-3">
        <img src="../assets/logo.svg" height="100" width="100" />
      </div>
      <div class="text-left">
        <h1 class="mb-0 mt-0">User1</h1>
        <p class="mb-0 mt-0">
          In publishing and graphic design, Lorem ipsum is a placeholder text
          commonly used to demonstrate the visual form of a document or a
          typeface without relying on meaningful content. Lorem ipsum may be
          used as a placeholder before final copy is available
        </p>
      </div>
    </div>
    <div class="d-flex align-items-center">
      <div class="mr-3">
        <img src="../assets/logo1.png" height="100" width="100" />
      </div>
      <div class="text-left">
        <h1 class="mb-0 mt-0">User2</h1>
        <p class="mb-0 mt-0">
          In publishing and graphic design, Lorem ipsum is a placeholder text
          commonly used to demonstrate the visual form of a document or a
          typeface without relying on meaningful content. Lorem ipsum may be
          used as a placeholder before final copy is available
        </p>
      </div>
    </div>
    <div class="d-flex align-items-center">
      <div class="mr-3">
        <img src="../assets/logo.svg" height="100" width="100" />
      </div>
      <div class="text-left">
        <h1 class="mb-0 mt-0">User1</h1>
        <p class="mb-0 mt-0">
          In publishing and graphic design, Lorem ipsum is a placeholder text
          commonly used to demonstrate the visual form of a document or a
          typeface without relying on meaningful content. Lorem ipsum may be
          used as a placeholder before final copy is available
        </p>
      </div>
    </div>
    <div class="d-flex align-items-center">
      <div class="mr-3">
        <img src="../assets/logo1.png" height="100" width="100" />
      </div>
      <div class="text-left">
        <h1 class="mb-0 mt-0">User2</h1>
        <p class="mb-0 mt-0">
          In publishing and graphic design, Lorem ipsum is a placeholder text
          commonly used to demonstrate the visual form of a document or a
          typeface without relying on meaningful content. Lorem ipsum may be
          used as a placeholder before final copy is available
        </p>
      </div>
    </div>
    <div class="d-flex align-items-center">
      <div class="mr-3">
        <img src="../assets/logo.svg" height="100" width="100" />
      </div>
      <div class="text-left">
        <h1 class="mb-0 mt-0">User1</h1>
        <p class="mb-0 mt-0">
          In publishing and graphic design, Lorem ipsum is a placeholder text
          commonly used to demonstrate the visual form of a document or a
          typeface without relying on meaningful content. Lorem ipsum may be
          used as a placeholder before final copy is available
        </p>
      </div>
    </div>
    <div>
      <QuillEditor :toolbarOptions="toolbar" />
    </div>
  </div>
</template>
<script>
// import QuillEditor from "./QuillEditor.vue";
import QuillEditor from "./QuillEditor.vue";
export default {
  data() {
    return {};
  },
  components: { QuillEditor },
};
</script>
<style scoped>
.d-flex {
  display: flex;
  align-items: center;
}
.text-left {
  text-align: left;
}
.mb-0 {
  margin-bottom: 0px;
}
.mt-0 {
  margin-top: 0px;
}
.mr-3 {
  margin-right: 0.75rem !important;
}
</style>
