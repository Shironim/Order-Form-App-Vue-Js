<template>
  <div id="card">
    <div id="card-content">
      <div id="card-title">
        <h2>Register</h2>
        <!-- <div class="underline-title"></div> -->
      </div>
      <form method="post" class="form">
        <label for="user-name" style="padding-top:13px">&nbsp;Username</label>
        <input
          id="user-name"
          class="form-content"
          type="text"
          name="username"
          autocomplete="on"
          required
        />
        <div class="form-border"></div>
        <label for="user-email" style="padding-top:13px">&nbsp;Email</label>
        <input
          id="user-email"
          class="form-content"
          type="email"
          name="email"
          autocomplete="on"
          required
        />
        <div class="form-border"></div>
        <label for="user-password" style="padding-top:22px">&nbsp;Password</label>
        <input id="user-password" class="form-content" type="password" name="password" required />
        <div class="form-border"></div>

        <input id="submit-btn" type="submit" name="submit" value="Sign Up" />
        <!-- <a href="#" id="signup">Don't have account yet?</a> -->
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name:'CardRegister',
  component: {
    // 
  }
}
</script>

<style scoped>
a {
  text-decoration: none;
}
body {
  background: -webkit-linear-gradient(bottom, #2dbd6e, #a6f77b);
  background-repeat: no-repeat;
}
label {
  font-family: "Raleway", sans-serif;
  font-size: 11pt;
}
#forgot-pass {
  color: #2dbd6e;
  font-family: "Raleway", sans-serif;
  font-size: 10pt;
  margin-top: 3px;
  text-align: right;
}
#card {
  background: #fbfbfb;
  border-radius: 8px;
  box-shadow: 1px 2px 8px rgba(0, 0, 0, 0.65);
  height: auto;
  margin: 6rem auto 8.1rem auto;
  width: 329px;
}
#card-content {
  padding: 22px 44px;
}
#card-title {
  font-family: "Raleway Thin", sans-serif;
  letter-spacing: 4px;
  padding-bottom: 23px;
  padding-top: 13px;
  text-align: center;
}
#signup {
  color: #2dbd6e;
  font-family: "Raleway", sans-serif;
  font-size: 10pt;
  margin-top: 16px;
  text-align: center;
}
#submit-btn {
  background: -webkit-linear-gradient(right, #a6f77b, #2dbd6e);
  border: none;
  border-radius: 21px;
  box-shadow: 0px 1px 8px #24c64f;
  cursor: pointer;
  color: white;
  font-family: "Raleway SemiBold", sans-serif;
  height: 42.3px;
  margin: 0 auto;
  margin-top: 50px;
  transition: 0.25s;
  width: 153px;
}
#submit-btn:hover {
  box-shadow: 0px 1px 18px #24c64f;
}
.form {
  align-items: left;
  display: flex;
  flex-direction: column;
}
.form-border {
  background: -webkit-linear-gradient(right, #a6f77b, #2ec06f);
  height: 1px;
  width: 100%;
}
.form-content {
  background: #fbfbfb;
  border: none;
  outline: none;
  padding-top: 14px;
}
.underline-title {
  background: -webkit-linear-gradient(right, #a6f77b, #2ec06f);
  height: 2px;
  margin: -1.1rem auto 0 auto;
  width: 89px;
}
</style>