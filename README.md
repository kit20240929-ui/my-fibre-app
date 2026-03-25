HTML
<!DOCTYPE html>
<html>
<head>
  <title>Fibre Apply System</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      font-family: Arial;
      background: #0f172a;
      color: white;
      margin: 0;
    }

    .section {
      padding: 15px;
      margin-bottom: 20px;
    }

    .title {
      font-size: 22px;
      font-weight: bold;
      margin-bottom: 10px;
    }

    img {
      width: 100%;
      border-radius: 10px;
      margin-bottom: 10px;
    }

    input, select, textarea {
      width: 100%;
      padding: 10px;
      margin: 6px 0;
      border-radius: 6px;
      border: none;
    }

    button {
      background: #25D366;
      color: white;
      padding: 14px;
      border: none;
      border-radius: 8px;
      width: 100%;
      font-size: 16px;
      margin-top: 10px;
    }

    .time { background: #7c2d12; }
    .unifi { background: #1e3a8a; }
    .maxis { background: #14532d; }
  </style>
</head>

<body>

<!-- TIME -->
<div class="section time">
  <div class="title">🚀 TIME Fibre</div>
  <img src="time.jpg">

  <select id="timePackage">
    <option>Choose TIME Package</option>
    <option>200Mbps RM99</option>
    <option>600Mbps RM99 Promo 🔥</option>
    <option>1Gbps RM199</option>
    <option>2Gbps RM379</option>
  </select>
</div>

<!-- UNIFI -->
<div class="section unifi">
  <div class="title">📡 Unifi Fibre</div>
  <img src="unifi.jpg">

  <select id="unifiPackage">
    <option>Choose Unifi Package</option>
    <option>100Mbps RM89</option>
    <option>300Mbps RM129 🔥</option>
    <option>500Mbps RM149</option>
    <option>1Gbps RM249</option>
    <option>2Gbps RM319</option>
  </select>
</div>

<!-- MAXIS -->
<div class="section maxis">
  <div class="title">🟢 Maxis Fibre</div>
  <img src="maxis.jpg">

  <select id="maxisPackage">
    <option>Choose Maxis Package</option>
    <option>100Mbps RM89</option>
    <option>300Mbps RM99</option>
    <option>300Mbps RM129 (3 Months Free)</option>
    <option>500Mbps RM149 (3 Months Free)</option>
    <option>1Gbps RM249 (3 Months Free)</option>
  </select>
</div>

<!-- FORM -->
<div class="section">
  <div class="title">📝 Customer Details</div>

  <input type="text" id="name" placeholder="Name">
  <input type="text" id="phone1" placeholder="Phone 1">
  <input type="text" id="phone2" placeholder="Phone 2 (Optional)">
  <input type="email" id="email" placeholder="Email">
  <textarea id="address" placeholder="Address"></textarea>

  <button onclick="submitForm()">Submit & WhatsApp</button>
</div>

<script>
function submitForm() {
  let name = document.getElementById("name").value;
  let phone1 = document.getElementById("phone1").value;
  let phone2 = document.getElementById("phone2").value;
  let email = document.getElementById("email").value;
  let address = document.getElementById("address").value;

  let time = document.getElementById("timePackage").value;
  let unifi = document.getElementById("unifiPackage").value;
  let maxis = document.getElementById("maxisPackage").value;

  let selected = "";

  if (time !== "Choose TIME Package") {
    selected = "TIME - " + time;
  } else if (unifi !== "Choose Unifi Package") {
    selected = "UNIFI - " + unifi;
  } else if (maxis !== "Choose Maxis Package") {
    selected = "MAXIS - " + maxis;
  } else {
    alert("Please select a package!");
    return;
  }

  let message = 
`NEW CUSTOMER

Name: ${name}
Phone 1: ${phone1}
Phone 2: ${phone2}
Email: ${email}
Package: ${selected}
Address: ${address}`;

  let phone = "60172382477";

  window.open("https://wa.me/" + phone + "?text=" + encodeURIComponent(message));
}
</script>

</body>
</html>
