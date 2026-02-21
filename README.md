 <!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>514号室 意見箱</title>
</head>

<body style="background:black; color:#eee; font-family:monospace;">

<h2>高等中学 張瑞涵・514号室 意見箱</h2>
<div id="chat"></div>

<input id="msg" placeholder="願いは何ですか？">
<button onclick="reply()">送信</button>

<script>

// Lấy giờ hiện tại
let hour = new Date().getHours();

// Nếu đúng 0 giờ
if(hour === 0){
  document.body.innerHTML = `
    <div style="
      display:flex;
      justify-content:center;
      align-items:center;
      height:100vh;
      font-size:80px;
      color:red;
      background:black;
    ">
      514
    </div>
  `;
}

// Random response system in Japanese
function reply(){
  let input = document.getElementById("msg").value;
  let chat = document.getElementById("chat");

  chat.innerHTML += "<p>> " + input + "</p>";

  const replies = [
    "その願いは本物ですか？",
    "代償を払う覚悟はありますか？",
    "514号室はすべてを聞いています。",
    "願いは叶います。ただし、戻れません。",
    "それでも、望みますか？"
  ];

  setTimeout(()=>{
    let randomReply = replies[Math.floor(Math.random() * replies.length)];
    chat.innerHTML += "<p>Unknown: " + randomReply + "</p>";
  }, 1500);
}

</script>

</body>
</html>
