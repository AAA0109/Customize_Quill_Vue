<template>
  <div>
    <div class="position-relative" id="quillEditor">
      <quill-editor :options="editor_options" ref="quillEditor" />
    </div>
  </div>
</template>

<script>
import { quillEditor, Quill } from "vue-quill-editor";
import "quill/dist/quill.snow.css";
// import "quill/dist/quill.core.css";
// import "quill/dist/quill.bubble.css";
import "quill-emoji/dist/quill-emoji.css";
import "../quill-emoji/custom.css";
import QuillEmoji from "quill-emoji";
import TextareaEmoji from "../quill-emoji/module-textarea-emoji";

Quill.register("modules/emoji-shortname", QuillEmoji.ShortNameEmoji);
Quill.register("modules/emoji-textarea", TextareaEmoji)

export default {
  data() {
    return {
      editor_options: {
        modules: {
          toolbar: [
            [{ header: [false, 1, 2, 3, 4, 5, 6] }],
            ["bold", "italic", "underline", "strike"],
            [{ color: [] }, { background: [] }],
            ["blockquote", "code-block"],
            [{ list: "ordered" }, { list: "bullet" }],
            [{ script: "sub" }, { script: "super" }],
            [{ indent: "-1" }, { indent: "+1" }],
            [{ direction: "rtl" }, { align: [] }],
          ],
          "emoji-toolbar": true,
          "emoji-textarea": true,
          "emoji-shortname": true,
        },
      },
    };
  },
  components: { quillEditor }
};
</script>
