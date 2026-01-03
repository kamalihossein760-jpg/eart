<!doctype html>
<html lang="fa">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>مشخصات دوربین مدار بسته</title>
  <style>
    body {
      font-family: Tahoma, sans-serif;
      direction: rtl;
      padding:0;
      margin:0;
      background:#121212;
      color:#e0e0e0;
    }
    header {
      background:#1a1a1a;
      padding:15px 20px;
      text-align:center;
      font-size:24px;
      font-weight:bold;
      color:#ffffff;
      border-bottom: 2px solid #2196f3;
    }
    .container {
      padding:20px;
    }
    .card {
      max-width:800px;
      margin:20px auto;
      background:#1e1e2f;
      padding:20px;
      border-radius:10px;
      box-shadow:0 6px 20px rgba(0,0,0,0.5);
      border-left: 6px solid #2196f3;
    }
    .row {
      display:flex;
      gap:20px;
      flex-wrap:wrap;
    }
    .img-wrap {
      flex:0 0 320px;
      border-radius:6px;
      overflow:hidden;
      border: 2px solid #2196f3;
    }
    .img-wrap img {
      width:100%;
      display:block;
    }
    .info { flex:1; }
    h1 { margin-bottom:10px; color:#2196f3; }
    dl dt { font-weight:bold; margin-top:8px; color:#90caf9; }
    dl dd { margin:0 0 6px 0; }
  </style>
</head>
<body>
  <header>Pooya Jahesh</header>
  <div class="container">
    <div class="card" id="content"></div>
  </div>

  <script>
    const CAMERA = {
      title: "دوربین مدار بسته مدل Dome-2030",
      description: "دوربین دام مناسب فضاهای داخلی با کیفیت تصویر پایدار.",
      image: "https://libreshot.com/wp-content/uploads/2016/03/security-camera.jpg",
      specs: {
        "IP": "192.168.1.100",
        "Username": "admin",
        "Password": "123456",
        "مدل": "Dome-2030",
        "MAC Address": "00:1A:2B:3C:4D:5E",
        "Serial Number": "SN123456789"
      }
    };

    function render() {
      const c = document.getElementById("content");
      let specsHtml = "<dl>";
      for (const k in CAMERA.specs)
        specsHtml += `<dt>${k}</dt><dd>${CAMERA.specs[k]}</dd>`;
      specsHtml += "</dl>";

      c.innerHTML = `
        <div class="row">
          <div class="img-wrap"><img src="${CAMERA.image}" /></div>
          <div class="info">
            <h1>${CAMERA.title}</h1>
            <p>${CAMERA.description}</p>
            ${specsHtml}
          </div>
        </div>
      `;
    }

    render();
  </script>
</body>
</html>
