const SCRIPT_URL = "PASTE_YOUR_GOOGLE_WEB_APP_URL";

document.getElementById("feedbackForm").addEventListener("submit", function (e) {
  e.preventDefault();

  const formData = new URLSearchParams(new FormData(this));
  formData.append("SUBMITTED_ON", new Date().toLocaleString());

  fetch(SCRIPT_URL, {
    method: "POST",
    body: formData
  })
  .then(() => {
    alert("THANK YOU FOR YOUR VALUABLE FEEDBACK!");
    this.reset();
  })
  .catch(() => {
    alert("ERROR SUBMITTING FEEDBACK");
  });
});
