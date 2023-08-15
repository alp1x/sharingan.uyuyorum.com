<script setup>
  import { useChat } from 'ai/vue'
  const { messages, input, handleInputChange, handleSubmit, isLoading, reload } = useChat()

  const downloadIframeContent = (iframeContent) => {
    const blob = new Blob([iframeContent], { type: "text/html" });
    const url = URL.createObjectURL(blob);

    const a = document.createElement("a");
    a.href = url;
    a.download = "index.html";
    a.click();

    URL.revokeObjectURL(url);
  }
</script>

<template>
  <div class="container mx-auto">
  <div class="flex flex-col w-full max-w-md py-40 mx-auto stretch text-white">
    <div class="flex justify-center align-center">
      <Sharingan :isLoading="isLoading" />
      <Ascii />
    </div>
    <form @submit="handleSubmit" v-if="!isLoading" class="font-mono ml-40" >
      <label for="chat-input" class="sr-only">I'm your eyes..</label>
      <div class="relative">
        <textarea id="chat-input"
          class="block w-full resize-none rounded-xl border-none bg-black p-4 pr-16 text-sm text-slate-900 shadow-md focus:outline-none focus:ring-2 focus:ring-red-500 dark:bg-black dark:text-slate-200 dark:placeholder-slate-400 dark:focus:ring-red-500 sm:text-base"
          placeholder="I'm your eyes.." v-model="input" @change="handleInputChange" rows="1" required></textarea>
        <button
          class="absolute bottom-2 right-2.5 rounded-lg bg-gray-500 p-2 text-sm font-medium text-slate-200 hover:bg-red-500 focus:outline-none focus:ring-4 focus:ring-red-300 dark:bg-gray-500 dark:hover:bg-red-700 dark:focus:ring-red-800 sm:text-base">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" aria-hidden="true" viewBox="0 0 24 24" stroke-width="2"
            stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
            <path d="M10 14l11 -11"></path>
            <path d="M21 3l-6.5 18a.55 .55 0 0 1 -1 0l-3.5 -7l-7 -3.5a.55 .55 0 0 1 0 -1l18 -6.5"></path>
          </svg>
          <span class="sr-only">Send message</span>
        </button>
      </div>
    </form>
  </div>
  <div class="mx-auto mb-10">
    <div v-for="m in messages" :key="m.id">
      <div v-if="m.role === 'assistant' && m.content">
        <div class="flex flex-col items-center h-2/3 w-full">
          <div class="flex justify-center m-5">
              <button class="bg-red-800 rounded-lg text-center font-mono font-bold text-white p-5 hover:bg-green-800"
              @click="downloadIframeContent(m.content)"
              v-if="!isLoading && messages.length > 0">
              Download [index.html]
              <small class="block opacity-40">made with um-sharingan</small>
            </button>
            </div>
          <div class="border p-3 rounded-lg w-full border-orange-950">
            <div class="h-[36rem]">
              <iframe sandbox="allow-same-origin allow-scripts" :srcdoc="m.content" style="width: 100%; height: 100%;"></iframe>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<style>
body {
    background: #000;
}
body::-webkit-scrollbar {
    width: 0.3em;
}
body::-webkit-scrollbar-track {
    box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
}
body::-webkit-scrollbar-thumb {
    background-color: #7c7c7c;
    outline: 1px solid #7c7c7c;
}
::selection {
  color: #fff;
  background: #973636;
}
</style>