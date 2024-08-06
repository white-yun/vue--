<template>
    <div class="common-layout">
        <el-container>
            <el-header style="font-size: 30px;font-weight: bold;display: flex;justify-content: center;align-items: center;margin:20px 0">
<!--              <img src="../../assets/zxxc-logo.png" style="width: 30px;height: 30px" alt="" />-->
              安居乐寓智能客服大模型（测试集群）
            </el-header>
<!--            <el-container>-->
<!--                <el-aside width="200px">-->
<!--                  <el-row justify="start">-->
<!--                        <el-col :span="6">-->
<!--                            <el-text type="primary">模型 </el-text>-->
<!--                        </el-col>-->
<!--                        <el-col :span="14">-->
<!--                            <el-select v-model="state.model" class="m-2" placeholder="Select">-->
<!--                                <el-option v-for="(item, index) in state.models" :key="index" :label="item.label"-->
<!--                                    :value="item.value" />-->
<!--                            </el-select>-->
<!--                        </el-col>-->
<!--                    </el-row>-->
<!--                    <el-row justify="start">-->
<!--                        <el-col :span=6>-->
<!--                            <el-text>限制 </el-text>-->
<!--                        </el-col>-->
<!--                        <el-col :span="8" v-for="(item, index) in limits" :key="index">-->
<!--                            <el-text type="warning">{{ item }}</el-text>-->
<!--                        </el-col>-->
<!--                    </el-row>-->
<!--                    <el-row>-->
<!--                        <el-col :span="8" :offset="1">-->
<!--                            <el-tooltip content="设置获取到的apikey" placement="bottom" effect="light">-->
<!--                                <el-button @click="state.dialogVisible = true" type="success" size="small"-->
<!--                                    text="true">设置apiKey</el-button>-->
<!--                            </el-tooltip>-->
<!--                        </el-col>-->
<!--                        <el-col :span="8" :offset="1">-->
<!--                            <el-popconfirm title="确定要清除apiKey吗？">-->
<!--                                <template #reference>-->
<!--                                    <el-button @click="removeApiKey" type="danger" size="small"-->
<!--                                        text="true">清除apiKey</el-button>-->
<!--                                </template>-->
<!--                            </el-popconfirm>-->
<!--                        </el-col>-->
<!--                    </el-row>-->
<!--                    <el-row>-->
<!--                        <el-col :span="8" :offset="1">-->
<!--                            <el-tooltip content="设置要请求的后端的接口域名" placement="bottom" effect="light">-->
<!--                                <el-button @click="state.urlDialogVisible = true" type="success" size="small"-->
<!--                                    text="true">设置url前缀</el-button>-->
<!--                            </el-tooltip>-->
<!--                        </el-col>-->
<!--                        <el-col :span="8" :offset="1">-->
<!--                            <el-popconfirm title="确定要清除url前缀吗？">-->
<!--                                <template #reference>-->
<!--                                    <el-button @click="removeApiUrl" type="danger" size="small"-->
<!--                                        text="true">清除url前缀</el-button>-->
<!--                                </template>-->
<!--                            </el-popconfirm>-->
<!--                        </el-col>-->
<!--                    </el-row>-->
<!--                </el-aside>-->
                <el-main style="width: 100vw;padding: 0">
                    <div style="width: 100%;display: flex;justify-content: space-around;margin-bottom: 20px">
<!--                      <div style="width: 48vw;">-->
<!--                        <el-card>-->
<!--                          <el-scrollbar height="60vh">-->
<!--                            <div ref="chatDialog">-->
<!--                              <el-row v-for="(message, index) in state.chatHistory" :key="index">-->
<!--                                <el-divider />-->
<!--                                <el-col :span="2" v-if="message.role!=='user'">-->
<!--                                  <div style="display: flex;flex-direction: column;justify-content: center;align-items: center;">-->
<!--                                    <img src="../../assets/zxxc-logo.png" style="width: 30px;height: 30px" alt="" />-->
<!--                                    <el-text tag="b">HW</el-text>-->
<!--                                  </div>-->
<!--                                </el-col>-->
<!--                                <el-col :span="20" v-if="message.role!=='user'" style="display: flex;justify-content: flex-start;">-->
<!--                                  <v-md-preview style="text-align: left;background-color:rgba(244, 244, 244);color: #000000;border-radius: 16px;width: auto;display: flex;justify-content: flex-end" :text="message.content"></v-md-preview>-->
<!--                                </el-col>-->
<!--                                <el-col :span="20" v-if="message.role=='user'" style="display: flex;justify-content: flex-end;">-->
<!--                                  <v-md-preview style="text-align: left;background-color:rgba(244, 244, 244);color: #000000;border-radius: 16px;width: auto;display: flex;justify-content: flex-end" :text="message.content"></v-md-preview>-->
<!--                                </el-col>-->
<!--                                <el-col :span="2" v-if="message.role=='user'">-->
<!--                                  <div style="display: flex;flex-direction: column;justify-content: center;align-items: center;">-->
<!--                                    <img src="../../assets/role.png" style="width: 30px;height: 30px" alt="" />-->
<!--                                    <el-text tag="b">{{ message.role }} </el-text>-->
<!--                                  </div>-->
<!--                                </el-col>-->
<!--                              </el-row>-->
<!--                            </div>-->
<!--                            <div class="back-to-bottom" @click="scrollToBottom">-->
<!--                              <el-button type="primary" :icon="Bottom" circle></el-button>-->
<!--                            </div>-->
<!--                          </el-scrollbar>-->
<!--                          <el-progress :percentage="100" :show-text="false" v-show="state.loading" :indeterminate="true"-->
<!--                                       :duration="5" />-->
<!--                          <el-divider />-->

<!--                        </el-card>-->
<!--                      </div>-->
                      <div style="width: 80vw;">
                        <el-card>
                          <el-scrollbar height="60vh">
                            <div ref="chatDialog2">
                              <el-row v-for="(message, index) in state.chatHistory2" :key="index">
                                <el-divider />
                                <el-col :span="2" v-if="message.role!=='user'">
                                  <div style="display: flex;flex-direction: column;justify-content: center;align-items: center;">
                                    <img src="../../assets/role.png" style="width: 30px;height: 30px" alt="" />
                                    <el-text tag="b">安居乐寓</el-text>
                                  </div>
                                </el-col>
                                <el-col :span="20" v-if="message.role!=='user'" style="display: flex;justify-content: flex-start;">
                                  <v-md-preview style="text-align: left;background-color:rgba(244, 244, 244);color: #000000;border-radius: 16px;width: auto;display: flex;justify-content: flex-end" :text="message.content"></v-md-preview>
                                </el-col>
                                <el-col :span="20" v-if="message.role=='user'" style="display: flex;justify-content: flex-end;">
                                  <v-md-preview style="text-align: left;background-color:rgba(244, 244, 244);color: #000000;border-radius: 16px;width: auto;display: flex;justify-content: flex-end" :text="message.content"></v-md-preview>
                                </el-col>
                                <el-col :span="2" v-if="message.role=='user'">
                                  <div style="display: flex;flex-direction: column;justify-content: center;align-items: center;">
                                    <img src="../../assets/role.png" style="width: 30px;height: 30px" alt="" />
                                    <el-text tag="b">{{ message.role }} </el-text>
                                  </div>
                                </el-col>
                              </el-row>
                            </div>
                            <div class="back-to-bottom" @click="scrollToBottom2">
                              <el-button type="primary" :icon="Bottom" circle></el-button>
                            </div>
                          </el-scrollbar>
<!--                          <el-progress :percentage="100" :show-text="false" v-show="state.loading2" :indeterminate="true"-->
<!--                                       :duration="5" />-->
                          <el-divider />

                        </el-card>
                      </div>
                    </div>
                  <el-row>
                    <el-col :span="3">
                      <el-text tag="b"></el-text>
                    </el-col>
                    <el-col :span="14">
                      <el-input type="textarea" :autosize="{ minRows: 4, maxRows: 15 }" @keydown.enter="chatCompletion" placeholder="请输入您的问题..." v-model="state.content" clearable >
                      </el-input>
                    </el-col>
                    <el-col :span="2">
                      <el-button @click="chatCompletion">发送</el-button>
                    </el-col>
                    <el-col :span="2">
                      <el-popconfirm title="确定要清空聊天记录吗？" @confirm="removeHistoryChat">
                        <template #reference>
                          <el-button>清空聊天记录</el-button>
                        </template>
                      </el-popconfirm>
                    </el-col>
                  </el-row>
                </el-main>
          <view style="color: #7d7d7d">大模型 也可能会犯错。请核查重要信息。</view>
<!--            </el-container>-->
        </el-container>
    </div>

    <el-dialog v-model="state.dialogVisible" title="设置apiKey" width="30%">
        <el-row>
            <el-col>
                <el-input v-model="state.apiKey"></el-input>
            </el-col>
        </el-row>
        <template #footer>
            <span class="dialog-footer">
                <el-button @click="state.dialogVisible = false">关闭</el-button>
                <el-button type="primary" @click="setApiKey">
                    确认
                </el-button>
            </span>
        </template>
    </el-dialog>
    <el-dialog v-model="state.urlDialogVisible" title="设置apiKey" width="30%">
        <el-row>
            <el-col>
                <el-input v-model="state.apiUrl"></el-input>
            </el-col>
        </el-row>
        <template #footer>
            <span class="dialog-footer">
                <el-button @click="state.urlDialogVisible = false">关闭</el-button>
                <el-button type="primary" @click="setApiUrl">
                    确认
                </el-button>
            </span>
        </template>
    </el-dialog>

</template>
<script lang="ts" setup>

import axios from 'axios';
import { onMounted, reactive, computed, ref, nextTick } from 'vue';
import { ElMessage } from 'element-plus';
import { API_URL,API_URL2 } from '../../utils/env/constants';
import {
    Bottom
} from '@element-plus/icons-vue';


const state = reactive({
    content: '',
    models: [] as { label: string; value: string }[],
    model: 'gpt-4',
    modelMaps: {} as Record<string, { endpoints: string; limits: string[] }>,
    apiKey: '',
    chatHistory: [] as { role: string; content: string }[],
    dialogVisible: false,
    loading: false,
    urlDialogVisible: false,
    apiUrl: API_URL,
  models2: [] as { label: string; value: string }[],
  model2: 'gpt-4',
  modelMaps2: {} as Record<string, { endpoints: string; limits2: string[] }>,
  apiKey2: '',
  chatHistory2: [] as { role: string; content: string }[],
  dialogVisible2: false,
  loading2: false,
  urlDialogVisible2: false,
  apiUrl2: API_URL2,
  conversation_id:"a06cc6da-625f-443a-bb79-f8ff9946bda6"

});
const chatDialog = ref<HTMLElement | null>(null);
const chatDialog2 = ref<HTMLElement | null>(null);
onMounted(() => {
    // getModels();
    // 从本地存储中读取聊天记录
  axios({
    method: 'post',
    // url: `${state.apiUrl}${state.modelMaps[state.model].endpoints}`,
    url:'https://qianfan.baidubce.com/v2/app/conversation',
    data: {
      app_id: "6c4aed3f-d82d-432b-9c52-0e1e045f28cd"
    },
    headers: {
      'Content-Type': 'application/json',
      Authorization: `Bearer bce-v3/ALTAK-nZyCv9CnD6iUfi1JoHASm/c7196afeb6ac314bf481f02ba421be877e312bf8`,

    },
    // responseType: 'stream'
  }).then(res => {
    state.conversation_id=res.data.conversation_id || "a06cc6da-625f-443a-bb79-f8ff9946bda6";
    console.log(res)
  })
    const storedChatHistory = localStorage.getItem('chatHistory');
    if (storedChatHistory) {
        state.chatHistory = JSON.parse(storedChatHistory);
    }
    const storedApiKey = localStorage.getItem('apiKey');
    if (storedApiKey) {
        state.apiKey = storedApiKey;
    }
    const storedApiUrl = localStorage.getItem('apiUrl');
    if (storedApiUrl) {
        state.apiUrl = storedApiUrl;
    }
  const storedChatHistory2 = localStorage.getItem('chatHistory2');
  if (storedChatHistory2) {
    state.chatHistory2 = JSON.parse(storedChatHistory2);
  }
  const storedApiKey2 = localStorage.getItem('apiKey2');
  if (storedApiKey2) {
    state.apiKey2 = storedApiKey2;
  }
  const storedApiUrl2 = localStorage.getItem('apiUrl2');
  if (storedApiUrl2) {
    state.apiUrl2 = storedApiUrl2;
  }
    scrollToBottom();
  scrollToBottom2();
})

const getConversation= async ()=>{
//   axios({
//     method: 'post',
//     // url: `${state.apiUrl}${state.modelMaps[state.model].endpoints}`,
//     url:'https://qianfan.baidubce.com/v2/app/conversation',
//     data: {
//       model: "chatglm3-6b",
//       messages: [
//         {"role": "user", "content": state.content}
//       ],
//       max_tokens: 500,
//       top_k: -1,
//       top_p: 1,
//       temperature: 0,
//       ignore_eos: false,
//       stream: false
//     },
//     headers: {
//       'Content-Type': 'application/json',
//       // Authorization: `Bearer ${state.apiKey}`
//     },
//     responseType: 'stream'
//   }).then(async response => {
}
/**
 * 监听模型是否改变
 */
const limits = computed(() => {
    if (state.modelMaps[state.model]) {
        return state.modelMaps[state.model].limits
    }
}
);
const limits2 = computed(() => {
      if (state.modelMaps2[state.model2]) {
        return state.modelMaps2[state.model2].limits2
      }
    }
);
const removeHistoryChat = () => {
  console.log("removeHistoryChat")
    localStorage.removeItem("chatHistory");
  state.chatHistory = [];
  localStorage.removeItem("chatHistory2");
  state.chatHistory2 = [];
}

const chatCompletion = async () => {
  // setMessage()
  sendMessage2()
}
const setMessage = async () => {
  try {
    let returnMsg = '';
    state.loading = true;
    // 在发送消息时，将消息添加到聊天历史中
    state.chatHistory.push({ role: 'user', content: state.content });

    scrollToBottom();
    axios({
      method: 'post',
      // url: `${state.apiUrl}${state.modelMaps[state.model].endpoints}`,
      url:'https://gallery.cn-southwest-2.myhuaweicloud.com/v1/gallery/3a898be8-b53d-4f66-9f46-9f797d9dabd2/',
      data: {
        model: "chatglm3-6b",
        messages: [
          {"role": "user", "content": state.content}
        ],
        max_tokens: 500,
        top_k: -1,
        top_p: 1,
        temperature: 0,
        ignore_eos: false,
        stream: false
      },
      headers: {
        'Content-Type': 'application/json',
        // Authorization: `Bearer ${state.apiKey}`
      },
      responseType: 'stream'
    }).then(async response => {
      // Create a new Blob object
      const blob = new Blob([response.data], { type: 'text/event-stream' });
      console.log(1111)
      // Create a new ReadableStream
      const stream = blob.stream();
      console.log(2222)
      // Create a new TextDecoder
      const decoder = new TextDecoder();
      console.log(3333)
      let chunkTextBuffer = ''; // Buffer to accumulate chunk text
      console.log(4444)
      // Function to process the chunks of data from the stream
      const processChunk = async (chunk: any) => {
        // Convert ArrayBuffer to string
        const chunkText = decoder.decode(chunk.value);
        console.log(5555)
        // Combine the current chunkText with previous buffered text
        chunkTextBuffer += chunkText;
        console.log(6666)
        console.log(chunkTextBuffer)
        // Process each line in the chunkTextBuffer
        const lines = chunkTextBuffer.split('\n');
        console.log("lines",lines)
        for (let i = 0; i < lines.length; i++) {
          console.log(7777)
          const line = lines[i];
          console.log("line.substring(6)",line.substring(6))
          try {
            const jsonData = JSON.parse(line);
            if (jsonData.choices && jsonData.choices.length > 0) {
              const firstChoice = jsonData.choices[0];
              if (firstChoice.message && firstChoice.message.content) {
                returnMsg += firstChoice.message.content;
              }
            }
            // if (line.startsWith('data: ')) {
            //   console.log(8888)
            //     const jsonData = JSON.parse(line.substring(6));
            //     if (jsonData.choices && jsonData.choices[0] && jsonData.choices[0].message && jsonData.choices[0].message.content) {
            //         returnMsg += jsonData.choices[0].message.content;
            //     }
            //   console.log("returnMsg:"+returnMsg)
            // }else {
            //   console.log(88888888)
            // }
          } catch (e) {
            console.log(9999)
            //returnMsg += '---over---';
            return;
          }
        }
        // Update the chunkTextBuffer with any remaining text
        chunkTextBuffer = lines[lines.length - 1];
      };
      // Continuously read chunks from the stream and process them
      const reader = stream.getReader();
      console.log("aaaaa")
      //异步方法
      const readChunks = async () => {
        while (true) {
          const { done, value } = await reader.read();
          if (done) break;
          await processChunk({ done, value });
        }

        // 在接收到回复时，将回复添加到聊天历史中
        state.chatHistory.push({ role: 'assistant', content: returnMsg });
        // 将聊天历史保存到本地存储中
        localStorage.setItem('chatHistory', JSON.stringify(state.chatHistory));
        state.loading = false;
        scrollToBottom();
      }
      state.content=''
      readChunks();
    }).catch(error => {
      console.log(error)
      ElMessage({
        message: "请求出错,返回数据:" + error.response.data,
        type: 'warning',
        duration: 5000
      })
      state.loading = false;
      scrollToBottom();
    });
  } catch (error) {
    console.log(error)
  }
}


const sendMessage2 = async () => {
  // try {
  //   state.loading2 = true;
  //   // 将消息添加到聊天历史中
  //   state.chatHistory2.push({ role: 'user', content: state.content });
  //   scrollToBottom2();
  //
  //   fetch('https://qianfan.baidubce.com/v2/app/conversation/runs', {
  //     method: 'POST',
  //     headers: {
  //       'Content-Type': 'application/json',
  //       Authorization: `Bearer bce-v3/ALTAK-nZyCv9CnD6iUfi1JoHASm/c7196afeb6ac314bf481f02ba421be877e312bf8`
  //     },
  //     body: JSON.stringify({
  //       app_id: "6c4aed3f-d82d-432b-9c52-0e1e045f28cd",
  //       query: state.content,
  //       stream: true,
  //       conversation_id: "0b93a8de-e9f1-4c3a-9daf-bebb0bdfce3b"
  //     })
  //   }).then(response => {
  //     let content = "";
  //     state.chatHistory2.push({ role: 'assistant', content: content });
  //     if (!response.ok) {
  //       throw new Error('Network response was not ok');
  //     }
  //
  //     // 读取响应体为一个ReadableStream
  //     const reader = response.body.getReader();
  //
  //     async function read() {
  //       const textDecoder = new TextDecoder();
  //       let chunkTextBuffer = '';
  //       let totalLength = 0;
  //       const baseDelay = 50; // 基础延时
  //       const minDelay = 10; // 最小延时
  //
  //       while (true) {
  //         const { done, value } = await reader.read();
  //         if (done) {
  //           console.log('Stream complete');
  //           break;
  //         }
  //
  //         const decodedChunk = textDecoder.decode(value);
  //         chunkTextBuffer += decodedChunk;
  //
  //         const lines = chunkTextBuffer.split('\n');
  //
  //         for (let i = 0; i < lines.length - 1; i++) {
  //           const line = lines[i].trim();
  //           if (line.startsWith('data: ')) {
  //             const jsonStart = line.indexOf('{');
  //             if (jsonStart !== -1) {
  //               const jsonData = JSON.parse(line.substring(jsonStart));
  //               if (jsonData.answer) {
  //                 for (let char of jsonData.answer) {
  //                   content += char;
  //                   state.chatHistory2[state.chatHistory2.length - 1].content = content;
  //                   scrollToBottom2();
  //                   totalLength++;
  //                   let delay = Math.max(minDelay, baseDelay - Math.log(totalLength + 1)); // 动态调整延时
  //                   await new Promise(resolve => setTimeout(resolve, delay));
  //                 }
  //               }
  //             }
  //           }
  //         }
  //
  //         chunkTextBuffer = lines[lines.length - 1];
  //       }
  //
  //       // 将聊天历史保存到本地存储中
  //       localStorage.setItem('chatHistory2', JSON.stringify(state.chatHistory2));
  //       state.loading2 = false;
  //       scrollToBottom2();
  //     }
  //
  //     state.content = '';
  //     read();
  //   }).catch(error => {
  //     console.error('Fetch error:', error);
  //     state.loading2 = false; // 确保在出错时更新加载状态
  //   });
  // } catch (error) {
  //   console.error('Try-catch error:', error);
  //   state.loading2 = false; // 确保在捕获到错误时更新加载状态
  // }

  try {
    state.loading2 = true;
    // 将消息添加到聊天历史中
    state.chatHistory2.push({ role: 'user', content: state.content });
    scrollToBottom2();
    let content = "";
    state.chatHistory2.push({ role: 'assistant', content: content });

    // 光标闪烁状态
    let cursorVisible = true;

    // 创建光标闪烁定时器
    const cursorInterval = setInterval(() => {
      cursorVisible = !cursorVisible;
      const cursor = cursorVisible ? "|" : "&nbsp;";
      const assistantMessage = state.chatHistory2[state.chatHistory2.length - 1];
      assistantMessage.content = content + cursor;

    }, 300);

    let content1=state.content
    state.content=""
    scrollToBottom2();
    fetch('https://qianfan.baidubce.com/v2/app/conversation/runs', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        Authorization: `Bearer bce-v3/ALTAK-nZyCv9CnD6iUfi1JoHASm/c7196afeb6ac314bf481f02ba421be877e312bf8`
      },
      body: JSON.stringify({
        app_id: "6c4aed3f-d82d-432b-9c52-0e1e045f28cd",
        query: content1,
        stream: true,
        conversation_id: state.conversation_id
      })
    }).then(response => {
      scrollToBottom2();
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }

      // 读取响应体为一个ReadableStream
      const reader = response.body.getReader();

      async function read() {
        const textDecoder = new TextDecoder();
        let chunkTextBuffer = '';
        let totalLength = 0;
        const baseDelay = 50; // 基础延时
        const threshold = 100; // 字符数量阈值

        while (true) {
          const { done, value } = await reader.read();
          if (done) {
            console.log('Stream complete');
            state.chatHistory2[state.chatHistory2.length - 1].content = content;
            clearInterval(cursorInterval);
            break;
          }

          const decodedChunk = textDecoder.decode(value);
          chunkTextBuffer += decodedChunk;

          const lines = chunkTextBuffer.split('\n');

          for (let i = 0; i < lines.length - 1; i++) {
            const line = lines[i].trim();
            if (line.startsWith('data: ')) {
              const jsonStart = line.indexOf('{');
              if (jsonStart !== -1) {
                const jsonData = JSON.parse(line.substring(jsonStart));
                if (jsonData.answer) {
                  if (content === "|") content = "";
                  for (let char of jsonData.answer) {
                    content += char + "|";
                    state.chatHistory2[state.chatHistory2.length - 1].content = content;
                    scrollToBottom2();
                    content = content.slice(0, -1); // 移除光标
                    totalLength++;
                    let delay = baseDelay;
                    if (totalLength > threshold) {
                      delay = baseDelay / Math.log(totalLength - threshold + Math.E); // 动态调整延时
                    }
                    await new Promise(resolve => setTimeout(resolve, delay));
                  }
                }
              }
            }
          }

          chunkTextBuffer = lines[lines.length - 1];
        }

        // 将聊天历史保存到本地存储中
        localStorage.setItem('chatHistory2', JSON.stringify(state.chatHistory2));
        state.loading2 = false;
        scrollToBottom2();
      }

      read();
       // 请求结束后清除光标闪烁定时器
    }).catch(error => {
      console.error('Fetch error:', error);
      state.loading2 = false; // 确保在出错时更新加载状态
    }).finally(() => {

    })

  } catch (error) {
    console.error('Try-catch error:', error);
    state.loading2 = false; // 确保在捕获到错误时更新加载状态
  }


  // try {
  //   let returnMsg = '';
  //   state.loading2 = true;
  //   // 在发送消息时，将消息添加到聊天历史中
  //   state.chatHistory2.push({ role: 'user', content: state.content });
  //   scrollToBottom2();
  //   axios({
  //     method: 'post',
  //     // url: `${state.apiUrl}${state.modelMaps[state.model].endpoints}`,
  //     url:'https://qianfan.baidubce.com/v2/app/conversation/runs',
  //     data: {
  //       app_id: "6c4aed3f-d82d-432b-9c52-0e1e045f28cd",
  //       query: state.content,
  //       stream: true,
  //       conversation_id: "0b93a8de-e9f1-4c3a-9daf-bebb0bdfce3b",
  //       // model: "chatglm3-6b",
  //       // messages: [
  //       //   {"role": "user", "content": state.content}
  //       // ],
  //       // max_tokens: 500,
  //       // top_k: -1,
  //       // top_p: 1,
  //       // temperature: 0,
  //       // ignore_eos: false,
  //       // stream: false
  //     },
  //     headers: {
  //       'Content-Type': 'application/json',
  //       Authorization: `Bearer bce-v3/ALTAK-nZyCv9CnD6iUfi1JoHASm/c7196afeb6ac314bf481f02ba421be877e312bf8`
  //     },
  //     // responseType: 'stream'
  //   }).then(async response => {
  //     // Create a new Blob object
  //     const blob = new Blob([response.data], { type: 'text/event-stream' });
  //     // Create a new ReadableStream
  //     const stream = blob.stream();
  //     // Create a new TextDecoder
  //     const decoder = new TextDecoder();
  //     let chunkTextBuffer = '';
  //
  //     const processChunk = async (chunk: any) => {
  //
  //       const chunkText = decoder.decode(chunk.value);
  //
  //       chunkTextBuffer += chunkText;
  //       // Process each line in the chunkTextBuffer
  //       const lines = chunkTextBuffer.split('\n');
  //       // console.log("lines",lines)
  //       for (let i = 0; i < lines.length; i++) {
  //         // console.log(7777);
  //         const line = lines[i].trim(); // Trim to remove any extra spaces
  //         // console.log("line.substring(6)", line.substring(6));
  //
  //         if (line.startsWith('data: ')) { // Ensure it's a line with data
  //           try {
  //             const jsonData = JSON.parse(line.substring(6));
  //             console.log("jsonData",jsonData)
  //             if (jsonData.answer && jsonData.answer.length > 0) {
  //               // const firstChoice = jsonData.answer[0];
  //               // if (firstChoice.data && firstChoice.data.answer) {
  //               returnMsg += jsonData.answer;
  //               // }
  //             }
  //           } catch (e) {
  //             // console.log(9999);
  //             // If parsing fails, skip the current line
  //             continue;
  //           }
  //         }
  //       }
  //
  //       chunkTextBuffer = lines[lines.length - 1];
  //     };
  //     // Continuously read chunks from the stream and process them
  //     const reader = stream.getReader();
  //     console.log("aaaaa")
  //     //异步方法
  //     const readChunks = async () => {
  //       while (true) {
  //         const { done, value } = await reader.read();
  //         if (done) break;
  //         await processChunk({ done, value });
  //       }
  //
  //       // 在接收到回复时，将回复添加到聊天历史中
  //       // state.chatHistory.push({ role: 'assistant', content: returnMsg });
  //       state.chatHistory2.push({ role: 'assistant', content: returnMsg });
  //       // 将聊天历史保存到本地存储中
  //       localStorage.setItem('chatHistory2', JSON.stringify(state.chatHistory));
  //       state.loading2 = false;
  //       scrollToBottom2();
  //     }
  //     state.content=''
  //     readChunks();
  //   }).catch(error => {
  //     console.log(error)
  //     ElMessage({
  //       message: "请求出错,返回数据:" + error.response.data,
  //       type: 'warning',
  //       duration: 5000
  //     })
  //     state.loading2 = false;
  //     scrollToBottom2();
  //   });
  // } catch (error) {
  //   console.log(error)
  // }

  // try {
  //   let returnMsg = '';
  //   state.loading2 = true;
  //   // 在发送消息时，将消息添加到聊天历史中
  //   state.chatHistory2.push({ role: 'user', content: state.content });
  //   scrollToBottom2();
  //
  //   axios({
  //     method: 'post',
  //     url: 'https://qianfan.baidubce.com/v2/app/conversation/runs',
  //     data: {
  //       app_id: "6c4aed3f-d82d-432b-9c52-0e1e045f28cd",
  //       query: state.content,
  //       stream: true,
  //       conversation_id: "0b93a8de-e9f1-4c3a-9daf-bebb0bdfce3b"
  //     },
  //     headers: {
  //       'Content-Type': 'application/json',
  //       Authorization: `Bearer bce-v3/ALTAK-nZyCv9CnD6iUfi1JoHASm/c7196afeb6ac314bf481f02ba421be877e312bf8`
  //     },
  //     responseType: 'stream'
  //   }).then(async response => {
  //     const reader = response.data.getReader();
  //     const decoder = new TextDecoder('utf-8');
  //     let chunkTextBuffer = '';
  //
  //     const processChunk = async (chunk) => {
  //       const chunkText = decoder.decode(chunk.value, { stream: true });
  //       chunkTextBuffer += chunkText;
  //       const lines = chunkTextBuffer.split('\n');
  //
  //       for (let i = 0; i < lines.length - 1; i++) {
  //         const line = lines[i].trim();
  //         if (line.startsWith('data: ')) {
  //           try {
  //             const jsonData = JSON.parse(line.substring(6));
  //             if (jsonData.answer && jsonData.answer.length > 0) {
  //               returnMsg += jsonData.answer;
  //               // 实时更新聊天历史
  //               state.chatHistory2.push({ role: 'assistant', content: returnMsg });
  //               scrollToBottom2();
  //             }
  //           } catch (e) {
  //             continue;
  //           }
  //         }
  //       }
  //
  //       chunkTextBuffer = lines[lines.length - 1];
  //     };
  //
  //     const readChunks = async () => {
  //       while (true) {
  //         const { done, value } = await reader.read();
  //         if (done) break;
  //         await processChunk({ done, value });
  //       }
  //
  //       // 在接收到所有数据后，将回复添加到聊天历史中
  //       state.chatHistory2.push({ role: 'assistant', content: returnMsg });
  //       // 将聊天历史保存到本地存储中
  //       localStorage.setItem('chatHistory2', JSON.stringify(state.chatHistory2));
  //       state.loading2 = false;
  //       scrollToBottom2();
  //     };
  //
  //     state.content = '';
  //     readChunks();
  //   }).catch(error => {
  //     console.log(error);
  //     ElMessage({
  //       message: "请求出错,返回数据:" + error.response.data,
  //       type: 'warning',
  //       duration: 5000
  //     });
  //     state.loading2 = false;
  //     scrollToBottom2();
  //   });
  // } catch (error) {
  //   console.log(error);
  // }

  // try {
  //   let returnMsg = '';
  //   state.loading2 = true;
  //   // 在发送消息时，将消息添加到聊天历史中
  //   state.chatHistory2.push({ role: 'user', content: state.content });
  //   scrollToBottom2();
  //
  //   axios({
  //     method: 'post',
  //     url: 'https://qianfan.baidubce.com/v2/app/conversation/runs',
  //     data: {
  //       app_id: "6c4aed3f-d82d-432b-9c52-0e1e045f28cd",
  //       query: state.content,
  //       stream: true,
  //       conversation_id: "0b93a8de-e9f1-4c3a-9daf-bebb0bdfce3b"
  //     },
  //     headers: {
  //       'Content-Type': 'application/json',
  //       Authorization: `Bearer bce-v3/ALTAK-nZyCv9CnD6iUfi1JoHASm/c7196afeb6ac314bf481f02ba421be877e312bf8`
  //     },
  //     // responseType: 'stream'
  //   }).then(async response => {
  //     const reader = response.data.getReader();
  //     const decoder = new TextDecoder('utf-8');
  //     let chunkTextBuffer = '';
  //
  //     // Continuously read chunks from the stream and process them
  //     const readChunks = async () => {
  //       while (true) {
  //         const { done, value } = await reader.read();
  //         if (done) break;
  //
  //         const chunkText = decoder.decode(value, { stream: true });
  //         chunkTextBuffer += chunkText;
  //         const lines = chunkTextBuffer.split('\n');
  //
  //         for (let i = 0; i < lines.length - 1; i++) {
  //           const line = lines[i].trim();
  //           if (line.startsWith('data: ')) {
  //             try {
  //               const jsonData = JSON.parse(line.substring(6));
  //               if (jsonData.answer && jsonData.answer.length > 0) {
  //                 returnMsg += jsonData.answer;
  //                 console.log("returnMsg=========",returnMsg)
  //                 // 实时更新聊天历史
  //                 if (state.chatHistory2[state.chatHistory2.length - 1].role === 'assistant') {
  //                   state.chatHistory2[state.chatHistory2.length - 1].content = returnMsg;
  //                 } else {
  //                   state.chatHistory2.push({ role: 'assistant', content: returnMsg });
  //                 }
  //                 scrollToBottom2();
  //               }
  //             } catch (e) {
  //               continue;
  //             }
  //           }
  //         }
  //         chunkTextBuffer = lines[lines.length - 1];
  //       }
  //       // 将聊天历史保存到本地存储中
  //       localStorage.setItem('chatHistory2', JSON.stringify(state.chatHistory2));
  //       state.loading2 = false;
  //       scrollToBottom2();
  //     };
  //
  //     state.content = '';
  //     readChunks();
  //   }).catch(error => {
  //     console.log(error);
  //     ElMessage({
  //       message: "请求出错,返回数据:" + error.response,
  //       type: 'warning',
  //       duration: 5000
  //     });
  //     state.loading2 = false;
  //     scrollToBottom2();
  //   });
  // } catch (error) {
  //   console.log(error);
  // }


}

const getModels = async () => {
    try {
        const response = await axios.get(
            `https://chimeragpt.adventblocks.cc/api/v1/models`);

        for (const item of response.data.data) {
            state.models.push({
                label: item.id,
                value: item.id
            })
            state.modelMaps[item.id] = {
                endpoints: item.endpoints[0],
                limits: item.limits
            };
        }
    } catch (error) {
        console.error('Error:', error);
    }

}

const setApiKey = () => {
    localStorage.setItem('apiKey', state.apiKey);
    state.dialogVisible = false
}

const removeApiKey = () => {
    state.apiKey = '';
    localStorage.removeItem('apiKey');
}

const removeApiUrl = () => {
    state.apiUrl = '';
    localStorage.removeItem('apiUrl');
}

const setApiUrl = () => {
    localStorage.setItem('apiUrl', state.apiUrl);
    state.urlDialogVisible = false
}



const scrollToBottom = async () => {
    await nextTick();
    if (chatDialog.value) {
        chatDialog.value.scrollIntoView(false);
    }
};
const scrollToBottom2 = async () => {
  await nextTick();
  if (chatDialog2.value) {
    chatDialog2.value.scrollIntoView(false);
  }
};
</script>

<style scoped>
.el-row {
    margin-bottom: 20px;
}

.back-to-bottom {
    right: 20px;
    bottom: 20px;
    position: absolute;
}
</style>