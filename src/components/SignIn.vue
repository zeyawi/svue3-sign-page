<template>
<div class="container">
  <div class="form-box" :style="{ left: isSignIn ? '0':'50%'}">
    <div v-show="isSignIn" class="sign-in-box">
      <h2>Sign In</h2>
      <div class="sign-icon">
        <span class="circle">f</span>
        <span class="circle">G+</span>
        <span class="circle">in</span>
      </div>
      <p>or using account</p>
      <form>
        <label>
          <input :maxlength="20" type="email" autocomplete="email" placeholder="e-mail">
        </label>
        <label>
          <input :maxlength="20" type="password" autocomplete="new-password" placeholder="password">
        </label>
        <label>
          <input type="submit" value="Sign In" @click="handleSubmit">
        </label>
      </form>
    </div>
    <div v-show="!isSignIn" class="sign-up-box">
      <h2>Sign Up</h2>
      <div class="sign-icon">
        <span class="circle">f</span>
        <span class="circle">G+</span>
        <span class="circle">in</span>
      </div>
      <p>sign up by email</p>
      <form>
        <label>
          <input :maxlength="20" type="email" autocomplete="email" placeholder="E-mail">
        </label>
        <label>
          <input :maxlength="20" type="password" autocomplete="new-password" placeholder="password">
        </label>
        <label>
          <input :maxlength="20" type="password" autocomplete="new-password" placeholder="confirm password">
        </label>
        <label>
          <input type="submit" value="Sign Up" @click.stop="handleSubmit">
        </label>
      </form>
    </div>
  </div>
  <div class="cover-box" :style="{ left: isSignIn ? '0':'-50%'}">
    <h2>hello friend</h2>
    <button class="switch-btn" @click="switchStatus">{{isSignIn ? 'Register':'Sign In'}}</button>
  </div>
</div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "SignIn",
  setup(){
    let isSignIn = ref(true);
    function switchStatus(){
      this.isSignIn = !this.isSignIn;
    }
    function handleSubmit(event){
      console.log(event);
      console.log('you submit!')
      alert('hello friend, sorry this is just a demo page');
    }
    return{
      isSignIn,
      switchStatus,
      handleSubmit,
    }
  }
}
</script>

<style lang="less" scoped>
.container{
  background: transparent;
  width: 50vw;
  height: 50vh;
  display: flex;
  .form-box{
    box-shadow: 0 0 10px aliceblue;
    width: 50%;
    background: aliceblue;
    position: relative;
    transition: all 0.5s ease-in-out;
    display: flex;
    justify-content: center;
    align-items: center;
    .sign-in-box,
    .sign-up-box{
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .sign-in-box h2,
    .sign-up-box h2{
      font-size: 30px;
      text-align: center;
    }
    .sign-in-box p,
    .sign-up-box p{
      text-align: center;
    }
    .sign-icon{
      display: flex;
      justify-content: center;
      align-items: center;
      span{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        border: 1px solid #aaa;
        margin: 15px 10px;
        cursor: pointer;
        &:hover{
          box-shadow: 0 0 4px #406ef4;
        }
      }
    }
    form{
      display: block;
      label{
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 25px 0;
        input{
          font-size: 18px;
          outline: none;
          padding: 8px 10px;
          width: 220px;
        }
        input[type="submit"]{
          width: 100px;
          border-radius: 20px;
          background: #df8266;
          border: none;
          cursor: pointer;
          &:hover{
            box-shadow: 0 0 5px #df8266;
          }
        }
      }
    }
  }
  .cover-box{
    box-shadow: 0 0 10px #ee7c5f;
    position: relative;
    transition: all 0.5s ease-in-out;
    width: 50%;
    background: #ee7c5f;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    h2{
      font-size: 30px;
    }
    .switch-btn{
      width: 100px;
      height: 40px;
      border: none;
      background: seashell;
      border-radius: 20px;
      margin: 40px 0;
      font-size: 18px;

      &:hover{
        box-shadow: 0 1px 5px #fff;
      }
    }
  }
}
</style>
