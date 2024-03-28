# iSCM-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>显示输入内容</title>
    <style>
        .error {
            color: red;
            visibility: hidden;
        }
        .logo-text {
            font-size: 36px; /* 设置字体大小为 36 像素 */
            font-weight: bold; /* 设置字体加粗 */
        }
        .logo-text .i {
            color: red; /* 设置 i 的颜色为红色 */
        }
        .logo-text .scm, .cloud-platform {
            color: blue; /* 设置字体颜色为蓝色 */
            font-size: 36px; /* 设置字体大小与 iSCM 相同 */
        }
        .container {
            text-align: center; /* 让容器内的内容居中显示 */
        }
        .input-container {
            text-align: left; /* 让输入框内的文本左对齐 */
            margin-left: auto; /* 将输入框左边距自动扩展 */
            margin-right: auto; /* 将输入框右边距自动扩展 */
            max-width: 220px; /* 设置输入框最大宽度 */
        }
        input {
            margin-bottom: 5px; /* 调整输入框之间的垂直间距 */
            width: 100%; /* 设置输入框宽度为容器宽度 */
        }
        @media screen and (max-width: 600px) {
            /* 在屏幕宽度小于 600px 时应用的样式 */
            .logo-text {
                font-size: 24px; /* 将字体大小调整为 24px */
            }
            .logo-text .scm, .cloud-platform {
                font-size: 24px; /* 将字体大小调整为 24px */
            }
            .input-container {
                max-width: 80%; /* 将输入框最大宽度调整为 80% */
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <span class="logo-text"><span class="i">i</span><span class="scm">SCM</span></span><span class="cloud-platform"> 雲平台</span><br> <!-- 显示 iSCM 字样 -->
        <div class="input-container">
            <input type="email" id="emailField" placeholder="请输入邮箱地址"><br>
            <span id="emailError" class="error">*</span><br>
        </div>
        <div class="input-container">
            <input type="password" id="passwordField" placeholder="请输入密码" onkeypress="checkEnter(event)"><br>
        </div>
        <button onclick="login()" id="loginButton">登录</button>
        <h1 id="displayTitle"></h1>
    </div>

    <script>
        function checkEnter(event) {
            // 当用户按下 Enter 键（keyCode为13）时
            if (event.keyCode === 13) {
                // 触发登录按钮的点击事件
                login();
            }
        }

        function login() {
            var email = document.getElementById("emailField").value;
            var password = document.getElementById("passwordField").value;

            if (email.indexOf('@') === -1) {
                alert("请输入正确的邮箱地址！");
                document.getElementById("emailError").style.visibility = "visible";
                return;
            } else {
                document.getElementById("emailError").style.visibility = "hidden";
                // 跳转到新页面
                window.location.href = "任務交辦個人回饋畫面.html";
            }
        }
    </script>
</body>
</html>
