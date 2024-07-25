<script setup lang="ts">
import EditorJS from '@editorjs/editorjs';
import Header from '@editorjs/header';
import Checklist from '@editorjs/checklist';
import EJLaTeX from 'editorjs-latex'; 
import List from '@editorjs/list';
import MathTool from 'editorjs-math';
import MathEditor from 'editorjs-mathlive';

const editor = new EditorJS(
  {
    holder: 'editorjs',
    tools: {
      header: {
        class: Header,
        shortcut: 'CMD+SHIFT+H',
      },
      checklist: {
        class: Checklist,
        inlineToolbar: true,
      },
      Math: {
        class: EJLaTeX,
        shortcut: 'CMD+SHIFT+L',
        config: {
          css: '.math-input { width: 100%; padding: 1rem; } .math-preview { text-align: center }'
        }
      },
      list: {
        class: List,
        inlineToolbar: true,
        config: {
          defaultStyle: 'unordered'
        }
      },
      mathEditor: {
        class: MathEditor,
        inlineToolbar: true,
        config: {
          virtualKeyboardMode: 'manual',
          defaultMode: 'math',
          smartMode:false,
          virtualKeyboardTheme:'material',
        },
      },
      math: {
        class: MathTool,
        config: {
          katex: {
            // 配置 KaTeX 选项
            macros: {
              "\\RR": "\\mathbb{R}"
            }
          }
        }
      }
    },
    data: {
      blocks: [
        {
          "type": "header",
          "data": {
            "text": "水ポンプの設計における重要な方程式",
            "level": 1
          }
        },
        {
          "type": "paragraph",
          "data": {
            "text": "水ポンプの設計において、ベルヌーイの方程式は非常に重要です。この方程式は、非圧縮性の摩擦のない流体に対して適用され、流線に沿ったエネルギーの保存を示しています。"
          }
        },
        {
          "type": "header",
          "data": {
            "text": "ベルヌーイの方程式",
            "level": 2
          }
        },
        {
          "type": "paragraph",
          "data": {
            "text": "ベルヌーイの方程式は以下のように表されます。この方程式により、流体の圧力、速度、および高さの関係を理解することができます。"
          }
        },
        {
          "type": "Math",
          "data": {
            "math": "P + \\frac{1}{2} \\rho v^2 + \\rho gh = \\text{一定}"
          }
        },
        {
          "type": "list",
          "data": {
            "style": "unordered",
            "items": [
              "P は圧力エネルギー（PaまたはN/m²）、",
              "ρ は流体の密度（kg/m³）、",
              "v は流体の速度（m/s）、",
              "g は重力加速度（9.81 m/s²）、",
              "h は高さ（m）を表します。"
            ]
          }
        },
      ]
    }
  });

</script>

<template>
  <main class="main">
    <h1>Editor.js</h1>
    <!-- <v-md-editor v-model="text" height="400px"></v-md-editor> -->
    <div id="editorjs"></div>

  </main>
</template>

<style scoped>
.main {
  padding: 2rem 3rem;
}

#editorjs {
  border-radius: 5px;
  border: 1px solid #ccc;
  border-bottom: none;
  padding: 1rem;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.math-input {
  width: 100%;
}

.cdx-block {
  background: black;
}
</style>
