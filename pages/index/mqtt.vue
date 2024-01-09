<template>
  <div class="websocket-container">
    <div class="websocket-form">
      <div class="header">
        <h2>Websocket</h2>
      </div>
      <div class="form-field">
        <label for="host">Host：</label>
        <input type="text" id="host" />
      </div>
      <div class="form-field">
        <label for="port">Port：</label>
        <input type="text" id="port" />
      </div>
      <div class="form-field">
        <label for="path">Path：</label>
        <input type="text" id="path" />
      </div>
      <div class="form-field">
        <label for="id">Client ID：</label>
        <input type="text" id="id" />
      </div>
      <div class="form-field">
        <label for="username">Username：</label>
        <input type="text" id="username" />
      </div>
      <div class="form-field">
        <label for="password">Password：</label>
        <input type="password" id="password" />
      </div>
      <div class="form-field">
        <label for="keep">Keep Alive：</label>
        <input type="text" id="keep" />
      </div>
      <div class="checkbox">
        <label class="checkbox">
          <input type="checkbox" id="clean" value="clean" />
          <text>Clean Session</text>
        </label>
        <label class="checkbox">
          <input type="checkbox" id="ssl" value="ssl" />
          <text>SSL</text>
        </label>
      </div>
      <p>ws://jqrjq.cn:8083/mqtt</p>
      <button class="btn-primary">Connect</button>
      <button class="btn-primary">Disconnect</button>
    </div>
  </div>
</template>

<script setup>
  // ...（您提供的脚本部分）
</script>

<style>
.websocket-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
 font-size: 12px;
}

.websocket-form {
  display: flex;
  flex-direction: column;
  width: 90%;
  max-width: 375px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f5f5f5;
  font-family: 'Helvetica', sans-serif;
  box-sizing: border-box;
}

.header {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'STSong', sans-serif;
  font-size: 25px;
  font-weight: bold;
}
.checkbox{
	padding-left: 40px;
	display: flex;
	font-size: 10px;
	flex-direction: row;
}
.form-field {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

label {
  flex-basis: 30%;
  text-align: right;
  font-weight: bold;
}
.form-field input{
	border: 1px solid #000;
}
input[type='text'],
input[type='password'],
select,
textarea {
  flex-grow: 1;
  padding: 5px;
  border: 1px solid #000;
  border-radius: 3px;
}

button {
  margin-top: 20px;
  padding: 10px;
  border: none;
  border-radius: 3px;
  background-color: #20abc4;
  color: #fff;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
  
}
text{
	padding-top: 6px;
}
</style>
