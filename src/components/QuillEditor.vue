<template>
  <div>
    <div class="position-relative" id="quillEditor">
      <quill-editor :options="editor_options" ref="quillEditor" />
    </div>
  </div>
</template>

<script>
import { quillEditor, Quill } from "vue-quill-editor";
import "quill/dist/quill.core.css";
import "quill/dist/quill.snow.css";
import "quill/dist/quill.bubble.css";
import "quill-emoji/dist/quill-emoji.css";
import "../quill-emoji/custom.css";
import QuillEmoji from "quill-emoji";
import TextareaEmoji from "../quill-emoji/module-textarea-emoji";

// Quill.register("modules/emoji-shortname", QuillEmoji.ShortNameEmoji);
Quill.register("modules/emoji-textarea", TextareaEmoji)

const RecentEmoji = function(quill, options) {
  const maxRecentEmoji = options.maxRecentEmoji || 10;
  const emojiList = options.emojiList || QuillEmoji.emojiList;
  const recentEmoji = [];

  // Load recent emoji from localStorage
  const storedRecentEmoji = localStorage.getItem("recentEmoji");
  if (storedRecentEmoji) {
    recentEmoji.unshift(...JSON.parse(storedRecentEmoji));
  }

  function updateRecentEmoji(value) {
    recentEmoji.unshift(value)
    if (recentEmoji.length > maxRecentEmoji) recentEmoji.shift();
    localStorage.setItem("recentEmoji", JSON.stringify(recentEmoji));
    // if (value in emojiList) {
    //   // Remove existing occurrence of emoji
    //   recentEmoji.splice(recentEmoji.indexOf(value), 1);
    //   // Add emoji to beginning of list
    //   recentEmoji.unshift(value);
    //   // Limit recent emoji list to `maxRecentEmoji`
    //   recentEmoji.splice(maxRecentEmoji);
    //   // Save recent emoji to localStorage
    //   localStorage.setItem("recentEmoji", JSON.stringify(recentEmoji));
    // }
  }

  quill.on("text-change", () => {
    const delta = quill.getContents().filter(op => op.insert && op.insert.emoji);
    const lastOp = delta[delta.length - 1];
    if(lastOp) {
      updateRecentEmoji(lastOp.insert.emoji);
    }
    // const delta = quill.getContents().filter(op => op.insert && typeof op.insert === "string");
    // const lastOp = delta[delta.length - 1];
    // if (lastOp && typeof lastOp.insert === "string") {
    //   const matches = lastOp.insert.match(/:[^:\s]*(?:::[^:\s]*)*:/g);
    //   if (matches) {
    //     matches.forEach(match => {
    //       updateRecentEmoji(match);
    //     });
    //   }
    // }
  });

  
  this.getRecentEmoji = function() {
    return recentEmoji.map(emoji => {
      return {
        value: emoji,
        label: emojiList[emoji],
        html: '',
      };
    });
  };

  // const btnEl = document.getElementsByClassName('textarea-emoji-control')[0];
  // if (btnEl) {
    
  // }
};

Quill.register("modules/recent-emoji", RecentEmoji);

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
            // ["emoji"],
          ],
          "emoji-toolbar": true,
          "emoji-textarea": true,
          "emoji-shortname": true,
          "recent-emoji": {
            maxRecentEmoji: 100,
          },
        },
      },
    };
  },
  components: { quillEditor }
};
</script>
