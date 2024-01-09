<template>
  <div class="container">
    <div class="userheader">
      <div class="logo-container">
        <img src="/只因.png" alt="" class="logo">
        <p class="membership">超级会员</p>
      </div>
      <p class="username">Super User</p>
    </div>
    <div class="content">
      <div class="card">
        <p class="value">0</p>
        <p class="label">待支付</p>
      </div>
      <div class="card">
        <p class="value">0</p>
        <p class="label">待收货</p>
      </div>
      <div class="card">
        <p class="value">0.00元</p>
        <p class="label">账户余额</p>
      </div>
    </div>
    <div class="footer">
      <p class="link">我的订单</p>
      <p class="arrow">></p>
    </div>
    <div class="footer">
      <p class="link">收货地址</p>
      <p class="arrow">></p>
    </div>
    <div class="footer">
      <p class="link" @click="logout">退出登录</p>
      <p class="arrow">></p>
    </div>
  </div>
</template>
<script>
 
 export default {
  methods: {
        logout(){
            const userStore = useUserStore();
            userStore.$reset();
            this.$router.push('/user/login');
        }
      }
 }
 
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  width: 90%;
  margin: 0 auto;
}

.userheader {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #d2b48c;
  margin-top: 30px;
  padding-top: 30px;
  padding-bottom: 20px;
  height: 150px;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  padding-bottom: 400px;
  max-width: 50px;
  max-height: 50px;
}

.membership {
  font-size: 14px;
  margin-left: 10px;
  margin-top: 100px;
}

.username {
  font-size: 14px;
  margin: 3px;
}

.content {
  flex: 1;
  display: flex;
}

.card {
  background-color: #d2b48c;
  flex: 1;
  padding: 20px;
  text-align: center;
}

.value {
  color: #000000;
  font-size: 14px;
  margin-bottom: 10px;
}

.label {
  font-size: 14px;
}

.footer {
  background-color: #d2b48c;
  padding: 20px;
  font-size: 14px;
  border-top: 1px solid #ffffff;
  display: flex;
}

.link {
  padding-left: 5%;
}

.arrow {
  margin-left: auto;
}
</style>
