<template>
  <div v-if="isShow" :class="notificationType === 'success' ? 'quick-toastify-successful-notification' : 'quick-toastify-warn-notification'">
    <div class="quick-toastify-alert-toast">
      <div class="quick-toastify-alert-container">
        <div class="quick-toastify-successfull-icon">
          <svg v-if="notificationType === 'success'" width="26" height="26" fill="none" viewBox="0 0 26 26" xmlns="http://www.w3.org/2000/svg"><path fill="#4BAE4F" fill-rule="evenodd" d="M13 0C5.83 0 0 5.83 0 13s5.83 13 13 13 13-5.83 13-13S20.17 0 13 0z" clip-rule="evenodd"/><path fill="#fff" fill-rule="evenodd" d="M19.287 8.618a.815.815 0 010 1.148l-7.617 7.617a.812.812 0 01-1.148 0l-3.808-3.809a.815.815 0 010-1.147.815.815 0 011.147 0l3.235 3.234 7.044-7.043a.806.806 0 011.147 0z" clip-rule="evenodd"/></svg>
          <svg v-else width="26" height="26" fill="none" viewBox="0 0 26 26" xmlns="http://www.w3.org/2000/svg"><path fill="#EC5956" fill-rule="evenodd" d="M26 13c0 7.18-5.82 13-13 13S0 20.18 0 13 5.82 0 13 0s13 5.82 13 13zm-11.375 6.5a1.625 1.625 0 11-3.25 0 1.625 1.625 0 013.25 0zM13 4.875c-.898 0-1.625.728-1.625 1.625V13a1.625 1.625 0 103.25 0V6.5c0-.897-.727-1.625-1.625-1.625z" clip-rule="evenodd"/></svg>
        </div>
        <p>{{ message }}</p>
        <div class="quick-toastify-cross-icon" @click="close">
          <svg width="10" height="10" fill="none" viewBox="0 0 10 10" xmlns="http://www.w3.org/2000/svg"><path fill="#686f7f" d="M.948 9.995a.94.94 0 01-.673-.23.966.966 0 010-1.352L8.317.278a.94.94 0 011.339.045c.323.35.342.887.044 1.258L1.611 9.765a.94.94 0 01-.663.23z"/><path fill="#686f7f" d="M8.98 9.995a.942.942 0 01-.664-.278L.275 1.582A.966.966 0 01.378.23a.939.939 0 011.232 0L9.7 8.366a.966.966 0 010 1.399.94.94 0 01-.72.23z"/></svg>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'QuickToastify',
  props: {
    notificationType: {
      type: String,
      default: 'success'
    },
    message: {
      type: String,
      default: 'Successfully Toasted!🤩'
    },
    isShow: {
      type: Boolean,
      default: true,
      required: true,
    },
    close:{
      type: Function,
      default: () =>{},
      required: true
    }
  },
  watch:{
    isShow(newValue){
      if(newValue){
        setTimeout(() => {
          this.close();
        }, 3000);
      }
    }
  }
};
</script>

<style scoped>
/* -------Notification alert toast------------ */

.quick-toastify-successful-notification {
    display: flex;
}

.quick-toastify-successful-notification .quick-toastify-alert-toast {
    position: fixed;
    top: 50px;
    right: 30px;
    z-index: 9999;
    -webkit-animation: quick-toastify-fadeinout 3s linear forwards;
    animation: quick-toastify-fadeinout 3s ease-in-out forwards;
}

.quick-toastify-successful-notification .quick-toastify-alert-toast .quick-toastify-alert-container {
    background: #ffffff;
    border: 1px solid #039855;
    box-shadow: 0px 7px 30px rgba(16, 5, 46, 0.08);
    border-radius: 10px;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    padding: 15px;
}

.quick-toastify-successful-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-successfull-icon,
.quick-toastify-successful-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon {
    height: 26px;
    width: 26px;
}

.quick-toastify-successful-notification .quick-toastify-alert-toast .quick-toastify-alert-container p {
    padding: 0 60px 0 13px;
}

.quick-toastify-successful-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon {
    background: #ffffff;
    border: 1px solid #e4e6eb;
    border-radius: 6px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}

.quick-toastify-successful-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon svg path {
    fill: #686f7f;
}

.quick-toastify-successful-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon:hover {
    background: #e4e6eb;
}

.quick-toastify-successful-notification.quick-toastify-hide {
    display: none;
}

/* -------Warn notification alert toast------------ */

.quick-toastify-warn-notification {
    display: flex;
}

.quick-toastify-warn-notification .quick-toastify-alert-toast {
    position: fixed;
    top: 120px;
    right: 30px;
    z-index: 9999;
    -webkit-animation: quick-toastify-fadeinout 3s linear forwards;
    animation: quick-toastify-fadeinout 3s ease-in-out forwards;
}

.quick-toastify-warn-notification .quick-toastify-alert-toast .quick-toastify-alert-container {
    background: #ffffff;
    border: 1px solid #ec0707;
    box-shadow: 0px 7px 30px rgba(16, 5, 46, 0.08);
    border-radius: 10px;
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    padding: 15px;
}

.quick-toastify-warn-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-successfull-icon,
.quick-toastify-warn-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon {
    height: 26px;
    width: 26px;
}

.quick-toastify-warn-notification .quick-toastify-alert-toast .quick-toastify-alert-container p {
    padding: 0 60px 0 13px;
}

.quick-toastify-warn-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon {
    background: #ffffff;
    border: 1px solid #e4e6eb;
    border-radius: 6px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}

.quick-toastify-warn-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon svg path {
    fill: #686f7f;
}

.quick-toastify-warn-notification .quick-toastify-alert-toast .quick-toastify-alert-container .quick-toastify-cross-icon:hover {
    background: #e4e6eb;
}

@-webkit-keyframes quick-toastify-fadeinout {
    0% {
        opacity: 0;
        top: 80px;
    }
    20%, 80% {
        opacity: 1;
        top: 50px;
    }
    100% {
        opacity: 0;
        top: 20px;
    }
}

@keyframes quick-toastify-fadeinout {
    0% {
        opacity: 0;
        top: 80px;
    }
    20%, 80% {
        opacity: 1;
        top: 50px;
    }
    100% {
        opacity: 0;
        top: 20px;
    }
}
</style>
