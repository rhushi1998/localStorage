# localStorage 

### HTML 
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <title>Information Card</title>
  </head>
  <body>
    <div class="container">
      <div id="info-card">
        <h1>User Information Card</h1>
        <div id="user-info">
          <div class="field">
            <span class="label">First Name:</span>
            <span id="first-name"></span>
          </div>
          <div class="field">
            <span class="label">Last Name:</span>
            <span id="last-name"></span>
          </div>
          <div class="field">
            <span class="label">Country:</span>
            <span id="country"></span>
          </div>
          <div class="field">
            <span class="label">Phone Number:</span>
            <span id="phone-number"></span>
          </div>
          <div class="field">
            <span class="label">State:</span>
            <span id="state"></span>
          </div>
          <div class="field">
            <span class="label">City:</span>
            <span id="city"></span>
          </div>
          <div class="field">
            <span class="label">Village:</span>
            <span id="village"></span>
          </div>
        </div>
      </div>
    </div>
    <script src="index.js"></script>
  </body>
</html> 

### JS
const storedUserInfo = localStorage.getItem("userInformation");
if (storedUserInfo) {
  const userInfo = JSON.parse(storedUserInfo);
  document.getElementById("first-name").textContent = userInfo.firstName;
  document.getElementById("last-name").textContent = userInfo.lastName;
  document.getElementById("country").textContent = userInfo.country;
  document.getElementById("phone-number").textContent = userInfo.phoneNumber;
  document.getElementById("state").textContent = userInfo.state;
  document.getElementById("city").textContent = userInfo.city;
  document.getElementById("village").textContent = userInfo.village;
}
function storeUserInfo() {
  const firstName = prompt("Enter your first name:");
  const lastName = prompt("Enter your last name:");
  const country = prompt("Enter your country:");
  const phoneNumber = prompt("Enter your phone number:");
  const state = prompt("Enter your state:");
  const city = prompt("Enter your city:");
  const village = prompt("Enter your village:");

  const userInfo = {
    firstName,
    lastName,
    country,
    phoneNumber,
    state,
    city,
    village,
  };

  localStorage.setItem("userInformation", JSON.stringify(userInfo));
  document.getElementById("first-name").textContent = userInfo.firstName;
  document.getElementById("last-name").textContent = userInfo.lastName;
  document.getElementById("country").textContent = userInfo.country;
  document.getElementById("phone-number").textContent = userInfo.phoneNumber;
  document.getElementById("state").textContent = userInfo.state;
  document.getElementById("city").textContent = userInfo.city;
  document.getElementById("village").textContent = userInfo.village;
}
storeUserInfo();
