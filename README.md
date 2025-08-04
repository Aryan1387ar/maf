<!DOCTYPE html>        <html lang="en">        
<head>        
  <meta charset="UTF-8" />        
  <title>Login | User Panel</title>        
  <style>        
    body {        
      font-family: Tahoma, sans-serif;        
      background: #f0f0f0;        
      padding: 20px;        
      margin: 0;        
    }        
    .card {        
      background: white;        
      padding: 20px;        
      max-width: 450px;        
      margin: 20px auto;        
      box-shadow: 0 0 10px #ccc;        
      border-radius: 10px;        
      box-sizing: border-box;        
      position: relative;        
    }        
    input, button {        
      width: 100%;        
      margin: 10px 0;        
      padding: 8px;        
      font-size: 16px;        
      box-sizing: border-box;        
    }        
    .admin-panel, .user-panel {        
      display: none;        
      margin-top: 20px;        
    }        
    .toggle {        
      display: flex;        
      align-items: center;        
      justify-content: space-between;        
      margin: 10px 0;        
    }        
    .toggle-switch {        
      position: relative;        
      width: 50px;        
      height: 24px;        
      background: #333;        
      border-radius: 12px;        
      cursor: pointer;        
    }        
    .toggle-switch input {        
      opacity: 0;        
      width: 0;        
      height: 0;        
    }        
    .slider {        
      position: absolute;        
      top: 2px;        
      left: 2px;        
      width: 20px;        
      height: 20px;        
      background: red;        
      border-radius: 50%;        
      transition: 0.3s;        
    }        
    /* وقتی سوییچ فعال است رنگ به سبز تغییر کند */        
    .toggle-switch input:checked + .slider {        
      transform: translateX(26px);        
      background: green;        
    }        
    #featureStatus {        
      color: green;        
      font-weight: bold;        
      margin-top: 10px;        
    }        
    #activeFeatures {        
      background: #f9f9f9;        
      padding: 10px;        
      border-radius: 8px;        
      margin-top: 15px;        
    }        
    #activeFeatures ul {        
      margin: 5px 0 0 0;        
      padding-left: 20px;        
    }        
    /* حذف موقعیت ثابت از connectionStatus و قرار دادن داخل پنل کاربر */        
    #connectionStatus {        
      font-weight: bold;        
      font-size: 14px;        
      color: red;        
      margin-bottom: 15px;        
    }        
    .user-expiry {        
      font-weight: bold;        
      margin-bottom: 15px;        
      font-size: 18px;        
    }        
    .user-expiry span {        
      color: #333;        
    }        
    .user-panel p {        
      font-size: 16px;        
    }        
    .admin-panel input[type="number"] {        
      margin-bottom: 10px;        
    }        
    .admin-user {        
      margin-bottom: 15px;        
      border-bottom: 1px solid #ddd;        
      padding-bottom: 10px;        
    }        
    .admin-user input[type="text"],        
    .admin-user input[type="password"],        
    .admin-user input[type="number"] {        
      width: 30%;        
      margin-right: 5px;        
      display: inline-block;        
    }        
    .admin-user label {        
      display: inline-block;        
      margin-right: 5px;        
      font-weight: bold;        
      vertical-align: middle;        
    }        
    .admin-user button {        
      width: auto;        
      display: inline-block;        
      padding: 6px 10px;        
      margin-left: 5px;        
      background: #e74c3c;        
      color: white;        
      border: none;        
      border-radius: 5px;        
      cursor: pointer;        
      font-size: 14px;        
    }        
    .admin-user button:hover {        
      background: #c0392b;        
    }        
  </style>        
</head>        
<body>        
  <div class="card" id="loginCard">          
  <h2>Login</h2>     
   <input type="text" id="username" placeholder="Username" autocomplete="off" />
    <input type="password" id="password" placeholder="Password" autocomplete="off" /
<div style="display: flex; align-items: center; gap: 10px; margin-top: 10px;">
  <label style="display: flex; align-items: center; gap: 300px; font-size: 20px;">
    <input type="checkbox" id="rememberMe" />
    <<< seve me
  </label>
  <button onclick="login()">Login</button>
</div>
<p id="loginError" style="color: red; font-weight: bold; margin-top: 10px;"></p>
<div class="card user-panel" id="userPanel">
    <h2>User Panel</h2>        <!-- وضعیت آنلاین/آفلاین اینجا -->        
<div id="connectionStatus">Offline</div>        
    
<p class="user-expiry">Subscription time left: <span id="timeLeft"></span></p>        
    
<div class="toggle"><label>AimFix</label><label class="toggle-switch"><input type="checkbox" onchange="toggleFeature(this, 'AimFix')"><span class="slider"></span></label></div>        
<div class="toggle"><label>AimBot</label><label class="toggle-switch"><input type="checkbox" onchange="toggleFeature(this, 'AimBot')"><span class="slider"></span></label></div>        
<div class="toggle"><label>AimLansXx</label><label class="toggle-switch"><input type="checkbox" onchange="toggleFeature(this, 'AimLansXx')"><span class="slider"></span></label></div>        
<div class="toggle"><label>Headtrick</label><label class="toggle-switch"><input type="checkbox" onchange="toggleFeature(this, 'Headtrick')"><span class="slider"></span></label></div>        
<div class="toggle"><label>No recoil</label><label class="toggle-switch"><input type="checkbox" onchange="toggleFeature(this, 'No recoil')"><span class="slider"></span></label></div>        
<div class="toggle"><label>Hs pescocinho</label><label class="toggle-switch"><input type="checkbox" onchange="toggleFeature(this, 'Hs pescocinho')"><span class="slider"></span></label></div>        
    
<div id="featureStatus"></div>        
<div id="activeFeatures">        
  <strong>Active Features:</strong>        
  <ul id="activeList"></ul>        
</div>        
    
<hr />        
<h3>Tutorial</h3>        
<p>Follow the steps as shown in the video.</p>        
<p>First, import the set into Game Guardian, then run the code as shown in the video. Make sure it loads.</p>        
<p><strong>Code:</strong> ðŸ˜´ Creditos: Drako.Xit XDPI = 99999.0 MOUSEX = OEM touchstart = OEM gesture/shape_detection = [x1,y1,x2,y2]\n ARROW_DOWN = OEM S_GESTURE = ("computer",400) LINE_HORIZONTAL_HESTURE = 888 LINE_DOWN_GESTURE = 785 C_GESTURE = ("computer",999) ARROW_UP = OEM ARROW_RIGHT = OEM GestureHorizontalv = diff Gesturedetector = keys </p>        
        
<button onclick="window.open('https://aparat.com/v/iho1q30')">Watch Tutorial</button>        
<button onclick="logout()">Logout</button>

  </div>          <div class="card admin-panel" id="adminPanel">        
    <h2>Admin Panel</h2>        
    <p>Welcome, Aryan!</p>        <input type="text" id="newUsername" placeholder="New Username" autocomplete="off" />        
<input type="text" id="newPassword" placeholder="New Password" autocomplete="off" /><br>        
    
<label>Subscription duration:</label><br>        
<input type="number" id="newDays" placeholder="Days" min="0" style="width: 48%; display: inline-block; margin-right: 4%;" />        
<input type="number" id="newHours" placeholder="Hours" min="0" max="23" style="width: 48%; display: inline-block;" /><br>        
    
<button onclick="addUser()">Add User</button>        
<div id="userList"></div>        
<button onclick="logout()">Logout</button>

  </div>        <script>        
  const adminUsername = "Aryan";        
  const adminPassword = "1";        
  const userUsername = "aryan";        
  const userPassword = "2";        
        
  // users array stores { username, password, expiry ISO string }        
  let users = JSON.parse(localStorage.getItem("users")) || [        
    { username: userUsername, password: userPassword, expiry: new Date(new Date().getTime() + 365*24*60*60*1000).toISOString() }        
  ];        
        
  // Login function        
function login() {
  const u = document.getElementById("username").value.trim();
  const p = document.getElementById("password").value.trim();
  const remember = document.getElementById("rememberMe").checked;

  // ادمین
  if (u === adminUsername && p === adminPassword) {
    if (remember) {
      localStorage.setItem("rememberedUsername", u);
      localStorage.setItem("rememberedPassword", p);
    } else {
      localStorage.removeItem("rememberedUsername");
      localStorage.removeItem("rememberedPassword");
    }
    showAdminPanel();
    return;
  }

  // کاربران عادی
  const found = users.find(user => user.username === u && user.password === p);

  if (found) {
    const today = new Date();
    const expiryDate = new Date(found.expiry);

    if (expiryDate < today) {
      document.getElementById("loginError").innerText = "⚠ .";
      return;
    }

    // ✅ ثبت زمان آخرین ورود
    found.lastLogin = new Date().toISOString();
    localStorage.setItem("users", JSON.stringify(users));

    if (remember) {
      localStorage.setItem("rememberedUsername", u);
      localStorage.setItem("rememberedPassword", p);
    } else {
      localStorage.removeItem("rememberedUsername");
      localStorage.removeItem("rememberedPassword");
    }

    showUserPanel(found);
  } else {
    document.getElementById("loginError").innerText = "❌ !";
  }
}
        
  // Show user panel with time left        
  function showUserPanel(user) {        
    document.getElementById("loginCard").style.display = "none";        
    document.getElementById("adminPanel").style.display = "none";        
    document.getElementById("userPanel").style.display = "block";        
    updateTimeLeft(user.expiry);        
    updateFeatureList();        
  }        
        
  // Show admin panel and load users        
  function showAdminPanel() {        
    document.getElementById("loginCard").style.display = "none";        
    document.getElementById("userPanel").style.display = "none";        
    document.getElementById("adminPanel").style.display = "block";        
    loadUsers();        
  }        
        
  // Update the time left (days and hours) in user panel        
  function updateTimeLeft(expiryISO) {        
    const now = new Date();        
    const expiry = new Date(expiryISO);        
    let diffMs = expiry - now;        
        
    if (diffMs <= 0) {        
      document.getElementById("timeLeft").textContent = "Subscription expired";        
      return;        
    }        
        
    const days = Math.floor(diffMs / (1000*60*60*24));        
    diffMs -= days * (1000*60*60*24);        
    const hours = Math.floor(diffMs / (1000*60*60));        
        
    document.getElementById("timeLeft").textContent = `${days} day${days !== 1 ? 's' : ''} and ${hours} hour${hours !== 1 ? 's' : ''} left`;        
  }        
        
  // Toggle features for user panel, store in sessionStorage        
  function toggleFeature(input, name) {        
    let activeFeatures = JSON.parse(sessionStorage.getItem("activeFeatures") || "[]");        
    const index = activeFeatures.indexOf(name);        
        
    if (input.checked && index === -1) {        
      activeFeatures.push(name);        
    } else if (!input.checked && index !== -1) {        
      activeFeatures.splice(index, 1);        
    }        
        
    sessionStorage.setItem("activeFeatures", JSON.stringify(activeFeatures));        
    updateFeatureList();        
  }        
        
  // Update feature list display        
  function updateFeatureList() {        
    let activeFeatures = JSON.parse(sessionStorage.getItem("activeFeatures") || "[]");        
    const list = document.getElementById("activeList");        
    list.innerHTML = "";        
    activeFeatures.forEach(f => {        
      const li = document.createElement("li");        
      li.textContent = f;        
      list.appendChild(li);        
    });        
    document.getElementById("featureStatus").textContent = activeFeatures.length > 0 ? "Features updated!" : "";        
  }        
        
  // Logout and reload page        
  function logout() {        
    location.reload();        
  }        
        
  // Add new user in admin panel        
  function addUser() {        
    const username = document.getElementById("newUsername").value.trim();        
    const password = document.getElementById("newPassword").value.trim();        
    const days = parseInt(document.getElementById("newDays").value);        
    const hours = parseInt(document.getElementById("newHours").value);        
        
    if (!username || !password || isNaN(days) || isNaN(hours) || hours < 0 || hours > 23) {        
      alert("Please fill all fields correctly.");        
      return;        
    }        
        
    // Calculate expiry date from now + days + hours        
    const expiryDate = new Date();        
    expiryDate.setDate(expiryDate.getDate() + days);        
    expiryDate.setHours(expiryDate.getHours() + hours);        
        
    // Check if username exists; if so, update else add new        
    const userIndex = users.findIndex(u => u.username === username);        
    if (userIndex >= 0) {        
      users[userIndex].password = password;        
      users[userIndex].expiry = expiryDate.toISOString();        
    } else {        
      users.push({ username, password, expiry: expiryDate.toISOString() });        
    }        
        
    localStorage.setItem("users", JSON.stringify(users));        
    loadUsers();        
        
    // Clear input fields        
    document.getElementById("newUsername").value = "";        
    document.getElementById("newPassword").value = "";        
    document.getElementById("newDays").value = "";        
    document.getElementById("newHours").value = "";        
  }        
        
  // Load users list in admin panel with editable days and hours        
 function loadUsers() {
  const listDiv = document.getElementById("userList");
  listDiv.innerHTML = "<h3>Users:</h3>";

  users.forEach((user, i) => {
    const now = new Date();
    const expiry = new Date(user.expiry);
    let diffMs = expiry - now;
    if (diffMs < 0) diffMs = 0;

    const daysLeft = Math.floor(diffMs / (1000 * 60 * 60 * 24));
    diffMs -= daysLeft * (1000 * 60 * 60 * 24);
    const hoursLeft = Math.floor(diffMs / (1000 * 60 * 60));

    // تاریخ آخرین ورود را تبدیل به فرمت خوانا کن
    const lastLogin = user.lastLogin
      ? new Date(user.lastLogin).toLocaleString("fa-IR")
      : "⛔ هرگز وارد نشده";

    listDiv.innerHTML += `
      <div class="admin-user" style="margin-bottom: 15px; padding: 10px; border-bottom: 1px solid #ccc;">
        <input type="text" value="${user.username}" placeholder="Username" onchange="editUser(${i}, 'username', this.value)" />
        <input type="text" value="${user.password}" placeholder="Password" onchange="editUser(${i}, 'password', this.value)" />
        <label>Days:</label>
        <input type="number" min="0" max="3650" value="${daysLeft}" onchange="editUserExpiry(${i}, this.value, 'days')" />
        <label>Hours:</label>
        <input type="number" min="0" max="23" value="${hoursLeft}" onchange="editUserExpiry(${i}, this.value, 'hours')" />
        <button onclick="deleteUser(${i})" title="Delete User">Delete</button>
        <div style="margin-top: 5px; color: #555;">🕓 login : <strong>${lastLogin}</strong></div>
      </div>
    `;
  });
}
        
  // Edit user field (username or password)        
  function editUser(index, key, value) {        
    users[index][key] = value.trim();        
    localStorage.setItem("users", JSON.stringify(users));        
  }        
        
  // Edit expiry days/hours for user        
  function editUserExpiry(index, value, type) {        
    const val = parseInt(value);        
    if (isNaN(val) || val < 0) return;        
        
    // Calculate new expiry based on now + days + hours        
    const now = new Date();        
        
    let daysLeft = 0, hoursLeft = 0;        
        
    // Get current expiry time difference        
    const expiry = new Date(users[index].expiry);        
    let diffMs = expiry - now;        
    if (diffMs < 0) diffMs = 0;        
        
    daysLeft = Math.floor(diffMs / (1000*60*60*24));        
    diffMs -= daysLeft * (1000*60*60*24);        
    hoursLeft = Math.floor(diffMs / (1000*60*60));        
        
    if (type === "days") daysLeft = val;        
    else if (type === "hours") hoursLeft = Math.min(val, 23);        
        
    const newExpiry = new Date();        
    newExpiry.setDate(newExpiry.getDate() + daysLeft);        
    newExpiry.setHours(newExpiry.getHours() + hoursLeft);        
        
    users[index].expiry = newExpiry.toISOString();        
    localStorage.setItem("users", JSON.stringify(users));        
    loadUsers();        
  }        
        
  // Delete user from list        
  function deleteUser(index) {        
    if (!confirm("Are you sure you want to delete this user?")) return;        
    users.splice(index, 1);        
    localStorage.setItem("users", JSON.stringify(users));        
    loadUsers();        
  }        
        
  // Update online/offline status        
  function updateConnectionStatus() {        
    const status = document.getElementById("connectionStatus");        
    if (navigator.onLine) {        
      status.textContent = "Online";        
      status.style.color = "green";        
    } else {        
      status.textContent = "Offline";        
      status.style.color = "red";        
    }        
  }        
        
  // Event listeners for online/offline        
  window.addEventListener("online", updateConnectionStatus);        
  window.addEventListener("offline", updateConnectionStatus);        
  updateConnectionStatus();        
        
  // Load active features from sessionStorage on load        
  window.onload = () => {
  updateFeatureList
  
  

  const savedU = localStorage.getItem("rememberedUsername");
  const savedP = localStorage.getItem("rememberedPassword");
  if (savedU && savedP) {
    document.getElementById("username").value = savedU;
    document.getElementById("password").value = savedP;
    document.getElementById("rememberMe").checked = true;
  }
};
</script>        </body>        
</html>       
